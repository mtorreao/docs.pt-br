---
title: Implementação de Gateways de API com o Ocelot
description: Saiba como implementar Gateways de API com o Ocelot e como usar o Ocelot em um ambiente baseado em contêiner.
ms.date: 03/02/2020
ms.openlocfilehash: 5da8533eff394b587d123970742727484a7236ad
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678124"
---
# <a name="implement-api-gateways-with-ocelot"></a><span data-ttu-id="bf8e1-103">Implementar Gateways de API com o Ocelot</span><span class="sxs-lookup"><span data-stu-id="bf8e1-103">Implement API Gateways with Ocelot</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf8e1-104">O aplicativo de desserviço de referência [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) está usando atualmente os recursos fornecidos pelo [Envoy](https://www.envoyproxy.io/) para implementar o gateway de API em vez do [Ocelot](https://github.com/ThreeMammals/Ocelot)referenciado anterior.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-104">The reference microservice application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) is currently using features provided by [Envoy](https://www.envoyproxy.io/) to implement the API Gateway instead of the earlier referenced [Ocelot](https://github.com/ThreeMammals/Ocelot).</span></span>
> <span data-ttu-id="bf8e1-105">Fizemos essa escolha de design devido ao suporte interno do Envoy para o protocolo WebSocket, exigido pelas novas comunicações entre serviços gRPC implementadas no eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-105">We made this design choice because of Envoy's built-in support for the WebSocket protocol, required by the new gRPC inter-service communications implemented in eShopOnContainers.</span></span>
> <span data-ttu-id="bf8e1-106">No entanto, reguardamos esta seção no guia para que você possa considerar o Ocelot como um gateway de API simples, compatível e leve, adequado para cenários de nível de produção.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-106">However, we've retained this section in the guide so you can consider Ocelot as a simple, capable, and lightweight API Gateway suitable for production-grade scenarios.</span></span>
> <span data-ttu-id="bf8e1-107">Além disso, a versão mais recente do Ocelot contém uma alteração significativa em seu esquema JSON.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-107">Also, latest Ocelot version contains a breaking change on its json schema.</span></span> <span data-ttu-id="bf8e1-108">Considere usar o Ocelot < v 16.0.0 ou usar as rotas de chave em vez de redirecionar.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-108">Consider using Ocelot < v16.0.0, or use the key Routes instead of ReRoutes.</span></span>

## <a name="architect-and-design-your-api-gateways"></a><span data-ttu-id="bf8e1-109">Arquitetar e projetar seus Gateways de API</span><span class="sxs-lookup"><span data-stu-id="bf8e1-109">Architect and design your API Gateways</span></span>

<span data-ttu-id="bf8e1-110">O diagrama de arquitetura a seguir mostra como os gateways de API foram implementados com Ocelot em eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-110">The following architecture diagram shows how API Gateways were implemented with Ocelot in eShopOnContainers.</span></span>

![Diagrama mostrando a arquitetura eShopOnContainers.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture.png)

<span data-ttu-id="bf8e1-112">**Figura 6-28**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-112">**Figure 6-28**.</span></span> <span data-ttu-id="bf8e1-113">Arquitetura do eShopOnContainers com Gateways de API</span><span class="sxs-lookup"><span data-stu-id="bf8e1-113">eShopOnContainers architecture with API Gateways</span></span>

<span data-ttu-id="bf8e1-114">Esse diagrama mostra como todo o aplicativo é implantado em um único host do Docker ou em um PC de desenvolvimento com "Docker for Windows" ou "Docker para Mac".</span><span class="sxs-lookup"><span data-stu-id="bf8e1-114">That diagram shows how the whole application is deployed into a single Docker host or development PC with "Docker for Windows" or "Docker for Mac".</span></span> <span data-ttu-id="bf8e1-115">No entanto, a implantação em qualquer orquestrador seria semelhante, mas qualquer contêiner no diagrama poderia ser escalado horizontalmente no orquestrador.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-115">However, deploying into any orchestrator would be similar, but any container in the diagram could be scaled out in the orchestrator.</span></span>

<span data-ttu-id="bf8e1-116">Além disso, os ativos de infraestrutura, como bancos de dados, cache e agentes de mensagens devem ser descarregados do orquestrador e implantados em sistemas altamente disponíveis para a infraestrutura, como o Banco de Dados SQL do Azure, o Azure Cosmos DB, o Redis do Azure, o Barramento de Serviço do Azure ou qualquer solução de cluster de HA local.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-116">In addition, the infrastructure assets such as databases, cache, and message brokers should be offloaded from the orchestrator and deployed into high available systems for infrastructure, like Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus, or any HA clustering solution on-premises.</span></span>

<span data-ttu-id="bf8e1-117">Como você também pode observar no diagrama, ter vários gateways de API permite que várias equipes de desenvolvimento sejam autônomas (neste caso, recursos de marketing versus recursos de compra) ao desenvolver e implantar seus microserviços, além de seus próprios gateways de API relacionados.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-117">As you can also notice in the diagram, having several API Gateways allows multiple development teams to be autonomous (in this case Marketing features vs. Shopping features) when developing and deploying their microservices plus their own related API Gateways.</span></span>

<span data-ttu-id="bf8e1-118">Se você tivesse um único Gateway de API monolítico, isso significaria um único ponto a ser atualizado por várias equipes de desenvolvimento, o que poderia vincular todos os microsserviços com uma única parte do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-118">If you had a single monolithic API Gateway that would mean a single point to be updated by several development teams, which could couple all the microservices with a single part of the application.</span></span>

<span data-ttu-id="bf8e1-119">Avançado bastante no design, às vezes, um Gateway de API refinado também pode ser limitado a um único microsserviço de negócios, dependendo da arquitetura escolhida.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-119">Going much further in the design, sometimes a fine-grained API Gateway can also be limited to a single business microservice depending on the chosen architecture.</span></span> <span data-ttu-id="bf8e1-120">Ter os limites do gateway de API ditados pelo negócio ou pelo domínio ajudará você a obter um design melhor.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-120">Having the API Gateway's boundaries dictated by the business or domain will help you to get a better design.</span></span>

<span data-ttu-id="bf8e1-121">Por exemplo, a granularidade refinada na camada do Gateway de API pode ser útil principalmente para aplicativos de interface do usuário compostos, mais avançados e baseados em microsserviços, porque o conceito de Gateway de API refinado é semelhante ao de serviço de composição de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-121">For instance, fine granularity in the API Gateway tier can be especially useful for more advanced composite UI applications that are based on microservices, because the concept of a fine-grained API Gateway is similar to a UI composition service.</span></span>

<span data-ttu-id="bf8e1-122">Apresentamos mais detalhes na seção anterior [Criando uma interface do usuário composta baseada em microsserviços](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span><span class="sxs-lookup"><span data-stu-id="bf8e1-122">We delve into more details in the previous section [Creating composite UI based on microservices](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span></span>

<span data-ttu-id="bf8e1-123">Como importante, para muitos aplicativos de médio e grande porte, usar um produto de gateway de API personalizado é geralmente uma boa abordagem, mas não como um agregador monolítico único ou gateway de API personalizada central exclusivo, a menos que o gateway de API permita várias áreas de configuração independentes para as várias equipes de desenvolvimento que criam microserviços autônomos.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-123">As a key takeaway, for many medium- and large-size applications, using a custom-built API Gateway product is usually a good approach, but not as a single monolithic aggregator or unique central custom API Gateway unless that API Gateway allows multiple independent configuration areas for the several development teams creating autonomous microservices.</span></span>

### <a name="sample-microservicescontainers-to-reroute-through-the-api-gateways"></a><span data-ttu-id="bf8e1-124">Microsserviços/contêineres de amostra a serem reencaminhados por meio dos Gateways de API</span><span class="sxs-lookup"><span data-stu-id="bf8e1-124">Sample microservices/containers to reroute through the API Gateways</span></span>

<span data-ttu-id="bf8e1-125">Por exemplo, o eShopOnContainers tem cerca de seis tipos de microsserviços internos que precisam ser publicados por meio dos Gateways de API, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-125">As an example, eShopOnContainers has around six internal microservice-types that have to be published through the API Gateways, as shown in the following image.</span></span>

![Captura de tela da pasta serviços mostrando suas subpastas.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-microservice-folders.png)

<span data-ttu-id="bf8e1-127">**Figura 6-29**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-127">**Figure 6-29**.</span></span> <span data-ttu-id="bf8e1-128">Pastas do microsserviço na solução eShopOnContainers no Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf8e1-128">Microservice folders in eShopOnContainers solution in Visual Studio</span></span>

<span data-ttu-id="bf8e1-129">Sobre o serviço de Identidade, no design, ele fica fora do roteamento do Gateway de API porque é o único interesse paralelo no sistema, embora com o Ocelot também seja possível incluí-lo como parte das listas de reencaminhamento.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-129">About the Identity service, in the design it's left out of the API Gateway routing because it's the only cross-cutting concern in the system, although with Ocelot it's also possible to include it as part of the rerouting lists.</span></span>

<span data-ttu-id="bf8e1-130">Todos esses serviços são implementados atualmente como serviços de API Web do ASP.NET Core, como você pode observar no código.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-130">All those services are currently implemented as ASP.NET Core Web API services, as you can tell from the code.</span></span> <span data-ttu-id="bf8e1-131">Vamos nos concentrar em um dos microserviços como o código de microserviço de catálogo.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-131">Let's focus on one of the microservices like the Catalog microservice code.</span></span>

![Captura de tela de Gerenciador de Soluções mostrando o conteúdo do projeto Catalog. API.](./media/implement-api-gateways-with-ocelot/catalog-api-microservice-folders.png)

<span data-ttu-id="bf8e1-133">**Figura 6-30**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-133">**Figure 6-30**.</span></span> <span data-ttu-id="bf8e1-134">Microsserviço de API Web de exemplo (microsserviço Catálogo)</span><span class="sxs-lookup"><span data-stu-id="bf8e1-134">Sample Web API microservice (Catalog microservice)</span></span>

<span data-ttu-id="bf8e1-135">Você pode ver que o microsserviço Catálogo é um projeto de API Web ASP.NET Core típico com vários controladores e métodos como no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-135">You can see that the Catalog microservice is a typical ASP.NET Core Web API project with several controllers and methods like in the following code.</span></span>

```csharp
[HttpGet]
[Route("items/{id:int}")]
[ProducesResponseType((int)HttpStatusCode.BadRequest)]
[ProducesResponseType((int)HttpStatusCode.NotFound)]
[ProducesResponseType(typeof(CatalogItem),(int)HttpStatusCode.OK)]
public async Task<IActionResult> GetItemById(int id)
{
    if (id <= 0)
    {
        return BadRequest();
    }
    var item = await _catalogContext.CatalogItems.
                                          SingleOrDefaultAsync(ci => ci.Id == id);
    //…

    if (item != null)
    {
        return Ok(item);
    }
    return NotFound();
}
```

<span data-ttu-id="bf8e1-136">A solicitação HTTP acabará executando esse tipo de código C# acessando o banco de dados de microsserviço e qualquer ação adicional necessária.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-136">The HTTP request will end up running that kind of C# code accessing the microservice database and any additional required action.</span></span>

<span data-ttu-id="bf8e1-137">Em relação à URL do Microservice, quando os contêineres são implantados em seu PC de desenvolvimento local (host do Docker local), cada contêiner de microserviço sempre tem uma porta interna (geralmente a porta 80) especificada em seu dockerfile, como no seguinte dockerfile:</span><span class="sxs-lookup"><span data-stu-id="bf8e1-137">Regarding the microservice URL, when the containers are deployed in your local development PC (local Docker host), each microservice's container always has an internal port (usually port 80) specified in its dockerfile, as in the following dockerfile:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
```

<span data-ttu-id="bf8e1-138">A porta 80 mostrada no código é interna no host do Docker e, portanto, não pode ser acessada por aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-138">The port 80 shown in the code is internal within the Docker host, so it can't be reached by client apps.</span></span>

<span data-ttu-id="bf8e1-139">Os aplicativos cliente poderão acessar apenas as portas externas (se houver) publicadas durante a implantação com `docker-compose`.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-139">Client apps can access only the external ports (if any) published when deploying with `docker-compose`.</span></span>

<span data-ttu-id="bf8e1-140">Essas portas externas não devem ser publicadas durante a implantação em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-140">Those external ports shouldn't be published when deploying to a production environment.</span></span> <span data-ttu-id="bf8e1-141">Por esse motivo específico, por que você deseja usar o gateway de API, para evitar a comunicação direta entre os aplicativos cliente e os microserviços.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-141">For this specific reason, why you want to use the API Gateway, to avoid the direct communication between the client apps and the microservices.</span></span>

<span data-ttu-id="bf8e1-142">No entanto, durante o desenvolvimento, é necessário acessar o microsserviço/contêiner diretamente e executá-lo por meio do Swagger.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-142">However, when developing, you want to access the microservice/container directly and run it through Swagger.</span></span> <span data-ttu-id="bf8e1-143">É por isso que, em eShopOnContainers, as portas externas ainda são especificadas mesmo quando não serão usadas pelo gateway de API ou pelos aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-143">That's why in eShopOnContainers, the external ports are still specified even when they won't be used by the API Gateway or the client apps.</span></span>

<span data-ttu-id="bf8e1-144">Aqui está um exemplo do `docker-compose.override.yml` arquivo para o microserviço de catálogo:</span><span class="sxs-lookup"><span data-stu-id="bf8e1-144">Here's an example of the `docker-compose.override.yml` file for the Catalog microservice:</span></span>

```yml
catalog-api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

<span data-ttu-id="bf8e1-145">Você pode ver como na configuração do docker-compose.override.yml a porta interna do contêiner de catálogo é a porta 80, mas a porta para acesso externo é a 5101.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-145">You can see how in the docker-compose.override.yml configuration the internal port for the Catalog container is port 80, but the port for external access is 5101.</span></span> <span data-ttu-id="bf8e1-146">Mas essa porta não deve ser usada pelo aplicativo ao usar um gateway de API, somente para depurar, executar e testar apenas o microserviço de catálogo.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-146">But this port shouldn't be used by the application when using an API Gateway, only to debug, run, and test just the Catalog microservice.</span></span>

<span data-ttu-id="bf8e1-147">Normalmente, você não estará implantando com Docker-Compose em um ambiente de produção porque o ambiente de implantação de produção certo para microserviços é um orquestrador como kubernetes ou Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-147">Normally, you won't be deploying with docker-compose into a production environment because the right production deployment environment for microservices is an orchestrator like Kubernetes or Service Fabric.</span></span> <span data-ttu-id="bf8e1-148">Ao implantar nesses ambientes, você usa arquivos de configuração diferentes em que você não publicará diretamente nenhuma porta externa para os microserviços, mas, sempre usará o proxy reverso do gateway de API.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-148">When deploying to those environments you use different configuration files where you won't publish directly any external port for the microservices but, you'll always use the reverse proxy from the API Gateway.</span></span>

<span data-ttu-id="bf8e1-149">Execute o microserviço de catálogo no host do Docker local.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-149">Run the catalog microservice in your local Docker host.</span></span> <span data-ttu-id="bf8e1-150">Execute a solução eShopOnContainers completa do Visual Studio (ela executa todos os serviços nos arquivos do Docker-Compose) ou inicie o microserviço de catálogo com o comando Docker-compote a seguir no CMD ou no PowerShell posicionado na pasta em que o `docker-compose.yml` e `docker-compose.override.yml` são colocados.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-150">Either run the full eShopOnContainers solution from Visual Studio (it runs all the services in the docker-compose files), or start the Catalog microservice with the following docker-compose command in CMD or PowerShell positioned at the folder where the `docker-compose.yml` and `docker-compose.override.yml` are placed.</span></span>

```console
docker-compose run --service-ports catalog-api
```

<span data-ttu-id="bf8e1-151">Esse comando só executa o contêiner do serviço Catalog-API, além das dependências especificadas no Docker-Compose. yml.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-151">This command only runs the catalog-api service container plus dependencies that are specified in the docker-compose.yml.</span></span> <span data-ttu-id="bf8e1-152">Nesse caso, o contêiner do SQL Server e o contêiner do RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-152">In this case, the SQL Server container and RabbitMQ container.</span></span>

<span data-ttu-id="bf8e1-153">Em seguida, você pode acessar diretamente o microserviço de catálogo e ver seus métodos por meio da interface do usuário do Swagger acessando diretamente por meio dessa porta "externa", neste caso `http://localhost:5101/swagger` :</span><span class="sxs-lookup"><span data-stu-id="bf8e1-153">Then, you can directly access the Catalog microservice and see its methods through the Swagger UI accessing directly through that "external" port, in this case `http://localhost:5101/swagger`:</span></span>

![Captura de tela da interface do usuário do Swagger mostrando a API REST do Catalog. API.](./media/implement-api-gateways-with-ocelot/test-catalog-microservice.png)

<span data-ttu-id="bf8e1-155">**Figura 6-31**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-155">**Figure 6-31**.</span></span> <span data-ttu-id="bf8e1-156">Testando o microsserviço Catálogo com sua interface do usuário do Swagger</span><span class="sxs-lookup"><span data-stu-id="bf8e1-156">Testing the Catalog microservice with its Swagger UI</span></span>

<span data-ttu-id="bf8e1-157">Neste ponto, você pode definir um ponto de interrupção no código C# no Visual Studio, testar o microsserviço com os métodos expostos na interface do usuário do Swagger e, por fim, limpar tudo com o comando `docker-compose down`.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-157">At this point, you could set a breakpoint in C# code in Visual Studio, test the microservice with the methods exposed in Swagger UI, and finally clean-up everything with the `docker-compose down` command.</span></span>

<span data-ttu-id="bf8e1-158">No entanto, a comunicação de acesso direto com o microsserviço, nesse caso, pela porta 5101 externa, é exatamente o que você deseja evitar em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-158">However, direct-access communication to the microservice, in this case through the external port 5101, is precisely what you want to avoid in your application.</span></span> <span data-ttu-id="bf8e1-159">E você pode evitar isso definindo o nível adicional de indireção do Gateway de API (o Ocelot, neste caso).</span><span class="sxs-lookup"><span data-stu-id="bf8e1-159">And you can avoid that by setting the additional level of indirection of the API Gateway (Ocelot, in this case).</span></span> <span data-ttu-id="bf8e1-160">Dessa forma, o aplicativo cliente não acessará diretamente o Microservice.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-160">That way, the client app won't directly access the microservice.</span></span>

## <a name="implementing-your-api-gateways-with-ocelot"></a><span data-ttu-id="bf8e1-161">Implementando Gateways de API com o Ocelot</span><span class="sxs-lookup"><span data-stu-id="bf8e1-161">Implementing your API Gateways with Ocelot</span></span>

<span data-ttu-id="bf8e1-162">O Ocelot é basicamente um conjunto de middleware que você pode aplicar em uma ordem específica.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-162">Ocelot is basically a set of middlewares that you can apply in a specific order.</span></span>

<span data-ttu-id="bf8e1-163">O Ocelot foi projetado para funcionar apenas com o ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-163">Ocelot is designed to work with ASP.NET Core only.</span></span> <span data-ttu-id="bf8e1-164">A versão mais recente do pacote é direcionada `.NETCoreApp 3.1` e, portanto, não é adequada para aplicativos .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-164">The latest version of the package targets `.NETCoreApp 3.1` and hence it is not suitable for .NET Framework applications.</span></span>

<span data-ttu-id="bf8e1-165">Instale o Ocelot e suas dependências no projeto ASP.NET Core com o [pacote NuGet do Ocelot](https://www.nuget.org/packages/Ocelot/), por meio do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-165">You install Ocelot and its dependencies in your ASP.NET Core project with [Ocelot's NuGet package](https://www.nuget.org/packages/Ocelot/), from Visual Studio.</span></span>

```powershell
Install-Package Ocelot
```

<span data-ttu-id="bf8e1-166">No eShopOnContainers, sua implementação de gateway de API é um projeto Webhost simples ASP.NET Core, e o middleware da Ocelot lida com todos os recursos do gateway de API, conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="bf8e1-166">In eShopOnContainers, its API Gateway implementation is a simple ASP.NET Core WebHost project, and Ocelot’s middleware handles all the API Gateway features, as shown in the following image:</span></span>

![Captura de tela de Gerenciador de Soluções mostrando o projeto de gateway de API do Ocelot.](./media/implement-api-gateways-with-ocelot/ocelotapigw-base-project.png)

<span data-ttu-id="bf8e1-168">**Figura 6-32**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-168">**Figure 6-32**.</span></span> <span data-ttu-id="bf8e1-169">Projeto base OcelotApiGw no eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="bf8e1-169">The OcelotApiGw base project in eShopOnContainers</span></span>

<span data-ttu-id="bf8e1-170">Este ASP.NET Core projeto Webhost é criado com dois arquivos simples:  `Program.cs` e `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="bf8e1-170">This ASP.NET Core WebHost project is built with two simple files:  `Program.cs` and `Startup.cs`.</span></span>

<span data-ttu-id="bf8e1-171">O Program.cs precisa apenas criar e configurar o BuildWebHost típico do ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-171">The Program.cs just needs to create and configure the typical ASP.NET Core BuildWebHost.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args)
        {
            var builder = WebHost.CreateDefaultBuilder(args);

            builder.ConfigureServices(s => s.AddSingleton(builder))
                    .ConfigureAppConfiguration(
                          ic => ic.AddJsonFile(Path.Combine("configuration",
                                                            "configuration.json")))
                    .UseStartup<Startup>();
            var host = builder.Build();
            return host;
        }
    }
}
```

<span data-ttu-id="bf8e1-172">O ponto importante para Ocelot é o arquivo `configuration.json` que você precisa fornecer para o construtor pelo método `AddJsonFile()`.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-172">The important point here for Ocelot is the `configuration.json` file that you must provide to the builder through the `AddJsonFile()` method.</span></span> <span data-ttu-id="bf8e1-173">Esse `configuration.json` é onde você especifica todos os reencaminhamentos do Gateway de API, o que significa os pontos de extremidade externos com portas específicas e os pontos de extremidade internos correlacionados, geralmente usando portas diferentes.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-173">That `configuration.json` is where you specify all the API Gateway ReRoutes, meaning the external endpoints with specific ports and the correlated internal endpoints, usually using different ports.</span></span>

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

<span data-ttu-id="bf8e1-174">Há duas seções para a configuração.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-174">There are two sections to the configuration.</span></span> <span data-ttu-id="bf8e1-175">Uma matriz de redirecionamentos e um GlobalConfiguration.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-175">An array of ReRoutes and a GlobalConfiguration.</span></span> <span data-ttu-id="bf8e1-176">As rerotas são os objetos que dizem ao Ocelot como tratar uma solicitação upstream.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-176">The ReRoutes are the objects that tell Ocelot how to treat an upstream request.</span></span> <span data-ttu-id="bf8e1-177">A configuração global permite substituições de redirecionar configurações específicas.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-177">The Global configuration allows overrides of ReRoute specific settings.</span></span> <span data-ttu-id="bf8e1-178">É útil se você não quiser gerenciar muitas configurações específicas de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-178">It's useful if you don't want to manage lots of ReRoute specific settings.</span></span>

<span data-ttu-id="bf8e1-179">Aqui está um exemplo simplificado de [redirecionar o arquivo de configuração](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) de um dos gateways de API do eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-179">Here's a simplified example of [ReRoute configuration file](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) from one of the API Gateways from eShopOnContainers.</span></span>

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/c/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ]
    },
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }

  ],
    "GlobalConfiguration": {
      "RequestIdKey": "OcRequestId",
      "AdministrationPath": "/administration"
    }
  }
```

<span data-ttu-id="bf8e1-180">A funcionalidade principal de um Gateway de API Ocelot é obter solicitações HTTP de entrada e encaminhá-las para um serviço downstream, simultaneamente à outra solicitação HTTP.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-180">The main functionality of an Ocelot API Gateway is to take incoming HTTP requests and forward them on to a downstream service, currently as another HTTP request.</span></span> <span data-ttu-id="bf8e1-181">Ocelot descreve o roteamento de uma solicitação para outra como uma redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-181">Ocelot's describes the routing of one request to another as a ReRoute.</span></span>

<span data-ttu-id="bf8e1-182">Por exemplo, vamos nos concentrar em uma das rerotas na configuration.jsacima, a configuração do microserviço basket.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-182">For instance, let's focus on one of the ReRoutes in the configuration.json from above, the configuration for the Basket microservice.</span></span>

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
}
```

<span data-ttu-id="bf8e1-183">O DownstreamPathTemplate, o esquema e o DownstreamHostAndPorts compõem a URL interna do microsserviço ao qual essa solicitação será encaminhada.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-183">The DownstreamPathTemplate, Scheme, and DownstreamHostAndPorts make the internal microservice URL that this request will be forwarded to.</span></span>

<span data-ttu-id="bf8e1-184">A porta é a porta interna usada pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-184">The port is the internal port used by the service.</span></span> <span data-ttu-id="bf8e1-185">Ao usar contêineres, é a porta especificada no dockerfile.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-185">When using containers, the port specified at its dockerfile.</span></span>

<span data-ttu-id="bf8e1-186">O `Host` é um nome de serviço que depende da resolução de nomes de serviço que você está usando.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-186">The `Host` is a service name that depends on the service name resolution you are using.</span></span> <span data-ttu-id="bf8e1-187">Quando o docker-compose é usado, os serviços de nomes são fornecidos pelo Host do Docker, que está usando os nomes de serviço fornecidos nos arquivos docker-compose.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-187">When using docker-compose, the services names are provided by the Docker Host, which is using the service names provided in the docker-compose files.</span></span> <span data-ttu-id="bf8e1-188">Quando é usado um orquestrador, como o Kubernetes ou o Service Fabric, esse nome deve ser resolvido pelo DNS ou pela resolução de nomes fornecida por cada orquestrador.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-188">If using an orchestrator like Kubernetes or Service Fabric, that name should be resolved by the DNS or name resolution provided by each orchestrator.</span></span>

<span data-ttu-id="bf8e1-189">DownstreamHostAndPorts é uma matriz que contém o host e a porta de todos os serviços downstream para os quais você deseja encaminhar solicitações.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-189">DownstreamHostAndPorts is an array that contains the host and port of any downstream services that you wish to forward requests to.</span></span> <span data-ttu-id="bf8e1-190">Normalmente, essa configuração conterá apenas uma entrada, mas às vezes você pode querer balancear a carga de solicitações para seus serviços downstream e o Ocelot permite que você adicione mais de uma entrada e, em seguida, selecione um balanceador de carga.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-190">Usually this configuration will just contain one entry but sometimes you might want to load balance requests to your downstream services and Ocelot lets you add more than one entry and then select a load balancer.</span></span> <span data-ttu-id="bf8e1-191">Mas se você estiver usando o Azure e algum orquestrador, provavelmente, será melhor balancear a carga com a infraestrutura de nuvem e do orquestrador.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-191">But if using Azure and any orchestrator it is probably a better idea to load balance with the cloud and orchestrator infrastructure.</span></span>

<span data-ttu-id="bf8e1-192">O UpstreamPathTemplate é a URL que o Ocelot usará para identificar qual DownstreamPathTemplate será usado para uma determinada solicitação do cliente.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-192">The UpstreamPathTemplate is the URL that Ocelot will use to identify which DownstreamPathTemplate to use for a given request from the client.</span></span> <span data-ttu-id="bf8e1-193">Por fim, o UpstreamHttpMethod é usado para que Ocelot possa distinguir entre diferentes solicitações (GET, POST, PUT) para a mesma URL.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-193">Finally, the UpstreamHttpMethod is used so Ocelot can distinguish between different requests (GET, POST, PUT) to the same URL.</span></span>

<span data-ttu-id="bf8e1-194">Neste ponto, você poderia usar um único Gateway de API do Ocelot (WebHost do ASP.NET Core), com um ou [vários arquivos configuration.json mesclados](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files), ou armazenar a [configuração em um repositório KV Consul](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span><span class="sxs-lookup"><span data-stu-id="bf8e1-194">At this point, you could have a single Ocelot API Gateway (ASP.NET Core WebHost) using one or [multiple merged configuration.json files](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) or you can also store the [configuration in a Consul KV store](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span></span>

<span data-ttu-id="bf8e1-195">Mas, conforme apresentado nas seções de arquitetura e design, se você realmente deseja usar microsserviços autônomos, talvez seja melhor dividir esse único Gateway de API monolítico em vários Gateways de API e/ou BFFs (back-end para front-end).</span><span class="sxs-lookup"><span data-stu-id="bf8e1-195">But as introduced in the architecture and design sections, if you really want to have autonomous microservices, it might be better to split that single monolithic API Gateway into multiple API Gateways and/or BFF (Backend for Frontend).</span></span> <span data-ttu-id="bf8e1-196">Para essa finalidade, vamos ver como implementar essa abordagem com contêineres do Docker.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-196">For that purpose, let's see how to implement that approach with Docker containers.</span></span>

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a><span data-ttu-id="bf8e1-197">Usando uma única imagem de contêiner do Docker para executar o vários Gateway de API diferentes ou tipos de BFF contêineres</span><span class="sxs-lookup"><span data-stu-id="bf8e1-197">Using a single Docker container image to run multiple different API Gateway / BFF container types</span></span>

<span data-ttu-id="bf8e1-198">No eShopOnContainers, estamos usando uma única imagem de contêiner do Docker com o gateway de API do Ocelot, mas então, em tempo de execução, criamos diferentes serviços/contêineres para cada tipo de API-Gateway/BFF fornecendo um configuration.jsdiferente no arquivo, usando um volume do Docker para acessar uma pasta de computador diferente para cada serviço.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-198">In eShopOnContainers, we're using a single Docker container image with the Ocelot API Gateway but then, at run time, we create different services/containers for each type of API-Gateway/BFF by providing a different configuration.json file, using a docker volume to access a different PC folder for each service.</span></span>

![Diagrama de uma única imagem do Docker de gateway Ocelot para todos os gateways de API.](./media/implement-api-gateways-with-ocelot/reusing-single-ocelot-docker-image.png)

<span data-ttu-id="bf8e1-200">**Figura 6-33**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-200">**Figure 6-33**.</span></span> <span data-ttu-id="bf8e1-201">Reutilizando uma única imagem do Docker do Ocelot em vários tipos de Gateway de API</span><span class="sxs-lookup"><span data-stu-id="bf8e1-201">Reusing a single Ocelot Docker image across multiple API Gateway types</span></span>

<span data-ttu-id="bf8e1-202">No eShopOnContainers, a "imagem do Docker do gateway de API Ocelot genérica" é criada com o projeto chamado ' OcelotApiGw ' e o nome da imagem "eshop/OcelotApiGw" que é especificado no arquivo Docker-Compose. yml.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-202">In eShopOnContainers, the "Generic Ocelot API Gateway Docker Image" is created with the project named 'OcelotApiGw' and the image name "eshop/ocelotapigw" that is specified in the docker-compose.yml file.</span></span> <span data-ttu-id="bf8e1-203">Em seguida, ao implantar no Docker, haverá quatro contêineres de Gateway de API criados com essa mesma imagem do Docker, conforme é mostrado na seguinte extração do arquivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-203">Then, when deploying to Docker, there will be four API-Gateway containers created from that same Docker image, as shown in the following extract from the docker-compose.yml file.</span></span>

```yml
  mobileshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  mobilemarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webmarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile
```

<span data-ttu-id="bf8e1-204">Além disso, como você pode ver no arquivo docker-compose.override.yml a seguir, a única diferença entre esses contêineres de Gateway de API é o arquivo de configuração do Ocelot, que é diferente para cada contêiner de serviço e é especificado em runtime por meio de um volume do Docker.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-204">Additionally, as you can see in the following docker-compose.override.yml file, the only difference between those API Gateway containers is the Ocelot configuration file, which is different for each service container and it's specified at runtime through a Docker volume.</span></span>

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

<span data-ttu-id="bf8e1-205">Devido ao código anterior e, como é mostrado no Gerenciador do Visual Studio abaixo, o único arquivo necessário para definir cada Gateway de API de negócios/BFF é apenas um arquivo configuration.json, porque os quatro Gateways de API são baseados na mesma imagem do Docker.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-205">Because of that previous code, and as shown in the Visual Studio Explorer below, the only file needed to define each specific business/BFF API Gateway is just a configuration.json file, because the four API Gateways are based on the same Docker image.</span></span>

![Captura de tela mostrando todos os gateways de API com configuration.jsem arquivos.](./media/implement-api-gateways-with-ocelot/ocelot-configuration-files.png)

<span data-ttu-id="bf8e1-207">**Figura 6-34**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-207">**Figure 6-34**.</span></span> <span data-ttu-id="bf8e1-208">O único arquivo necessário para definir cada Gateway de API/BFF com o Ocelot é um arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="bf8e1-208">The only file needed to define each API Gateway / BFF with Ocelot is a configuration file</span></span>

<span data-ttu-id="bf8e1-209">Dividindo o Gateway de API em vários Gateways de API, diferentes equipes de desenvolvimento concentrando-se em diferentes subconjuntos de microsserviços podem gerenciar seus próprios Gateways de API usando arquivos de configuração do Ocelot independentes.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-209">By splitting the API Gateway into multiple API Gateways, different development teams focusing on different subsets of microservices can manage their own API Gateways by using independent Ocelot configuration files.</span></span> <span data-ttu-id="bf8e1-210">Além disso, ao mesmo tempo, elas podem reutilizar a mesma imagem do Docker do Ocelot.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-210">Plus, at the same time they can reuse the same Ocelot Docker image.</span></span>

<span data-ttu-id="bf8e1-211">Agora, se você executar o eShopOnContainers com os gateways de API (incluídos por padrão no VS ao abrir a solução eShopOnContainers-ServicesAndWebApps. sln ou se estiver executando "Docker-compor"), as rotas de exemplo a seguir serão executadas.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-211">Now, if you run eShopOnContainers with the API Gateways (included by default in VS when opening eShopOnContainers-ServicesAndWebApps.sln solution or if running "docker-compose up"), the following sample routes will be performed.</span></span>

<span data-ttu-id="bf8e1-212">Por exemplo, ao visitar a URL upstream `http://localhost:5202/api/v1/c/catalog/items/2/` atendida pelo Gateway de API webshoppingapigw, você obterá o mesmo resultado da URL Downstream interna `http://catalog-api/api/v1/2` dentro do host do Docker, como no navegador a seguir.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-212">For instance, when visiting the upstream URL `http://localhost:5202/api/v1/c/catalog/items/2/` served by the webshoppingapigw API Gateway, you get the same result from the internal Downstream URL `http://catalog-api/api/v1/2` within the Docker host, as in the following browser.</span></span>

![Captura de tela de um navegador mostrando uma resposta que passa pelo gateway de API.](./media/implement-api-gateways-with-ocelot/access-microservice-through-url.png)

<span data-ttu-id="bf8e1-214">**Figura 6-35**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-214">**Figure 6-35**.</span></span> <span data-ttu-id="bf8e1-215">Acessando um microsserviço por meio de uma URL fornecida pelo Gateway de API</span><span class="sxs-lookup"><span data-stu-id="bf8e1-215">Accessing a microservice through a URL provided by the API Gateway</span></span>

<span data-ttu-id="bf8e1-216">Devido a motivos de teste ou depuração, se você quisesse acessar diretamente o contêiner do Docker do catálogo (somente no ambiente de desenvolvimento) sem passar pelo gateway de API, como ' Catalog-API ' é uma resolução de DNS interna ao host do Docker (descoberta de serviço manipulada por nomes de serviço do Docker-Compose), a única maneira de acessar diretamente o contêiner é por meio da porta externa publicada no Docker-Compose. Override. yml, que é fornecida somente para testes de desenvolvimento, como `http://localhost:5101/api/v1/Catalog/items/1` no navegador a seguir.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-216">Because of testing or debugging reasons, if you wanted to directly access to the Catalog Docker container (only at the development environment) without passing through the API Gateway, since 'catalog-api' is a DNS resolution internal to the Docker host (service discovery handled by docker-compose service names), the only way to directly access the container is through the external port published in the docker-compose.override.yml, which is provided only for development tests, such as `http://localhost:5101/api/v1/Catalog/items/1` in the following browser.</span></span>

![Captura de tela de um navegador que mostra uma resposta direta para o Catalog. API.](./media/implement-api-gateways-with-ocelot/direct-access-microservice-testing.png)

<span data-ttu-id="bf8e1-218">**Figura 6-36**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-218">**Figure 6-36**.</span></span> <span data-ttu-id="bf8e1-219">Acesso direto a um microsserviço para fins de teste</span><span class="sxs-lookup"><span data-stu-id="bf8e1-219">Direct access to a microservice for testing purposes</span></span>

<span data-ttu-id="bf8e1-220">Mas o aplicativo está configurado para que ele acesse todos os microserviços por meio dos gateways de API, não por meio da porta direta "atalhos".</span><span class="sxs-lookup"><span data-stu-id="bf8e1-220">But the application is configured so it accesses all the microservices through the API Gateways, not through the direct port "shortcuts".</span></span>

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a><span data-ttu-id="bf8e1-221">O padrão de agregação do Gateway em eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="bf8e1-221">The Gateway aggregation pattern in eShopOnContainers</span></span>

<span data-ttu-id="bf8e1-222">Conforme apresentado anteriormente, uma maneira flexível de implementar a agregação de solicitações é com os serviços personalizados, por código.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-222">As introduced previously, a flexible way to implement requests aggregation is with custom services, by code.</span></span> <span data-ttu-id="bf8e1-223">Você também pode implementar a agregação de solicitação com o [recurso de agregação de solicitação no Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), mas talvez não seja tão flexível quanto necessário.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-223">You could also implement request aggregation with the [Request Aggregation feature in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), but it might not be as flexible as you need.</span></span> <span data-ttu-id="bf8e1-224">Portanto, a maneira selecionada de implementar a agregação em eShopOnContainers é com um serviço de API Web explícito ASP.NET Core para cada agregador.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-224">Therefore, the selected way to implement aggregation in eShopOnContainers is with an explicit ASP.NET Core Web API service for each aggregator.</span></span>

<span data-ttu-id="bf8e1-225">De acordo com essa abordagem, o diagrama de composição do Gateway de API é, na realidade, um pouco mais amplo ao considerar os serviços de agregador que não são mostrados no diagrama de arquitetura global simplificado mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-225">According to that approach, the API Gateway composition diagram is in reality a bit more extended when considering the aggregator services that are not shown in the simplified global architecture diagram shown previously.</span></span>

<span data-ttu-id="bf8e1-226">No diagrama a seguir, você também poderá ver como os serviços do agregador funcionam com seus Gateways de API relacionados.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-226">In the following diagram, you can also see how the aggregator services work with their related API Gateways.</span></span>

![Diagrama da arquitetura eShopOnContainers que mostra os serviços do agregador.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture-aggregator-services.png)

<span data-ttu-id="bf8e1-228">**Figura 6-37**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-228">**Figure 6-37**.</span></span> <span data-ttu-id="bf8e1-229">Arquitetura de eShopOnContainers com serviços do agregador</span><span class="sxs-lookup"><span data-stu-id="bf8e1-229">eShopOnContainers architecture with aggregator services</span></span>

<span data-ttu-id="bf8e1-230">Ampliando ainda mais, na área de negócios de "compras" na imagem a seguir, você pode ver que a informação entre os aplicativos cliente e os microserviços é reduzida ao usar os serviços de agregador nos gateways de API.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-230">Zooming in further, on the "Shopping" business area in the following image, you can see that chattiness between the client apps and the microservices is reduced when using the aggregator services in the API Gateways.</span></span>

![Diagrama mostrando o zoom da arquitetura eShopOnContainers.](./media/implement-api-gateways-with-ocelot/zoom-in-vision-aggregator-services.png)

<span data-ttu-id="bf8e1-232">**Figura 6-38**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-232">**Figure 6-38**.</span></span> <span data-ttu-id="bf8e1-233">Visão ampliada do agregador de serviços</span><span class="sxs-lookup"><span data-stu-id="bf8e1-233">Zoom in vision of the Aggregator services</span></span>

<span data-ttu-id="bf8e1-234">Você pode observar como quando o diagrama mostra as possíveis solicitações provenientes dos gateways de API que podem ser complexas.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-234">You can notice how when the diagram shows the possible requests coming from the API Gateways it can get complex.</span></span> <span data-ttu-id="bf8e1-235">Por outro lado, ao usar o padrão de agregador, você pode ver como as setas em azul simplificariam a comunicação de uma perspectiva de aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-235">On the other hand, when you use the aggregator pattern, you can see how the arrows in blue would simplify the communication from a client app perspective.</span></span> <span data-ttu-id="bf8e1-236">Esse padrão não só ajuda a reduzir a informação e a latência na comunicação, além de melhorar significativamente a experiência do usuário para os aplicativos remotos (aplicativos móveis e SPA).</span><span class="sxs-lookup"><span data-stu-id="bf8e1-236">This pattern not only helps to reduce the chattiness and latency in the communication, it also improves the user experience significantly for the remote apps (mobile and SPA apps).</span></span>

<span data-ttu-id="bf8e1-237">No caso da área de negócios e dos microserviços de "marketing", é um caso de uso simples, portanto, não há necessidade de usar agregadores, mas também pode ser possível, se necessário.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-237">In the case of the "Marketing" business area and microservices, it is a simple use case so there was no need to use aggregators, but it could also be possible, if needed.</span></span>

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a><span data-ttu-id="bf8e1-238">Autenticação e autorização em Gateways de API do Ocelot</span><span class="sxs-lookup"><span data-stu-id="bf8e1-238">Authentication and authorization in Ocelot API Gateways</span></span>

<span data-ttu-id="bf8e1-239">Em um Gateway de API do Ocelot, você pode usar o serviço de autenticação, como um serviço de API Web ASP.NET Core, usando [IdentityServer](https://identityserver.io/) e fornecendo o token de autenticação dentro ou fora do Gateway de API.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-239">In an Ocelot API Gateway you can sit the authentication service, such as an ASP.NET Core Web API service using [IdentityServer](https://identityserver.io/) providing the auth token, either out or inside the API Gateway.</span></span>

<span data-ttu-id="bf8e1-240">Como o eShopOnContainers está usando vários Gateways de API com limites baseados em BFF e em áreas de negócios, o serviço de identidade/autenticação é deixado de fora dos Gateways de API, conforme está realçado em amarelo no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-240">Since eShopOnContainers is using multiple API Gateways with boundaries based on BFF and business areas, the Identity/Auth service is left out of the API Gateways, as highlighted in yellow in the following diagram.</span></span>

![Diagrama mostrando o microserviço de identidade sob o gateway de API.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-identity-service-position.png)

<span data-ttu-id="bf8e1-242">**Figura 6-39**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-242">**Figure 6-39**.</span></span> <span data-ttu-id="bf8e1-243">A posição do serviço de identidade em eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="bf8e1-243">Position of the Identity service in eShopOnContainers</span></span>

<span data-ttu-id="bf8e1-244">No entanto, o Ocelot também dá suporte ao uso do microsserviço de Identidade/Autenticação dentro do limite do Gateway de API, como neste outro diagrama.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-244">However, Ocelot also supports sitting the Identity/Auth microservice within the API Gateway boundary, as in this other diagram.</span></span>

![Diagrama mostrando a autenticação em um gateway de API do Ocelot.](./media/implement-api-gateways-with-ocelot/ocelot-authentication.png)

<span data-ttu-id="bf8e1-246">**Figura 6-40**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-246">**Figure 6-40**.</span></span> <span data-ttu-id="bf8e1-247">Autenticação no Ocelot</span><span class="sxs-lookup"><span data-stu-id="bf8e1-247">Authentication in Ocelot</span></span>

<span data-ttu-id="bf8e1-248">Como mostra o diagrama anterior, quando o microserviço de identidade está abaixo do gateway de API (AG): 1) o AG solicita um token de autenticação do microserviço de identidade, 2) o microserviço de identidade retorna token para AG, 3-4) solicitações AG de microserviços usando o token de autenticação.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-248">As the previous diagram shows, when the Identity microservice is beneath the API gateway (AG): 1) AG requests an auth token from identity microservice, 2) The identity microservice returns token to AG, 3-4) AG requests from microservices using the auth token.</span></span> <span data-ttu-id="bf8e1-249">Como o aplicativo eShopOnContainers dividiu o gateway de API em vários BFF (backend para front-end) e gateways de API de áreas de negócios, outra opção seria criar um gateway de API adicional para preocupações abrangentes.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-249">Because eShopOnContainers application has split the API Gateway into multiple BFF (Backend for Frontend) and business areas API Gateways, another option would have been to create an additional API Gateway for cross-cutting concerns.</span></span> <span data-ttu-id="bf8e1-250">Essa opção seria razoável em uma arquitetura de microsserviço bem mais complexa com vários microsserviços de interesses paralelos.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-250">That choice would be fair in a more complex microservice based architecture with multiple cross-cutting concerns microservices.</span></span> <span data-ttu-id="bf8e1-251">Como há apenas uma preocupação cruzada em eShopOnContainers, foi decidido simplesmente lidar com o serviço de segurança fora do realm do gateway de API, para simplificar a simplicidade.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-251">Since there's only one cross-cutting concern in eShopOnContainers, it was decided to just handle the security service out of the API Gateway realm, for simplicity's sake.</span></span>

<span data-ttu-id="bf8e1-252">Em qualquer caso, se o aplicativo estiver protegido no nível do Gateway de API, o módulo de autenticação do Gateway de API do Ocelot será acessado primeiro quando houver uma tentativa de usar qualquer microsserviço protegido.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-252">In any case, if the app is secured at the API Gateway level, the authentication module of the Ocelot API Gateway is visited at first when trying to use any secured microservice.</span></span> <span data-ttu-id="bf8e1-253">Isso redireciona a solicitação HTTP para visitar o microserviço de identidade ou autenticação para obter o token de acesso para que você possa visitar os serviços protegidos com o access_token.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-253">That redirects the HTTP request to visit the Identity or auth microservice to get the access token so you can visit the protected services with the access_token.</span></span>

<span data-ttu-id="bf8e1-254">É a maneira de proteger com autenticação qualquer serviço no nível do Gateway de API é definir o AuthenticationProviderKey em suas configurações relacionadas no configuration.json.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-254">The way you secure with authentication any service at the API Gateway level is by setting the AuthenticationProviderKey in its related settings at the configuration.json.</span></span>

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }
```

<span data-ttu-id="bf8e1-255">Quando o Ocelot for executado, ele examinará o redirecionations. AuthenticationProviderKey e verificará se há um provedor de autenticação registrado com a chave fornecida.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-255">When Ocelot runs, it will look at the ReRoutes AuthenticationOptions.AuthenticationProviderKey and check that there is an Authentication Provider registered with the given key.</span></span> <span data-ttu-id="bf8e1-256">Se não houver, o Ocelot não será iniciado.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-256">If there isn't, then Ocelot will not start up.</span></span> <span data-ttu-id="bf8e1-257">Se houver, o reencaminhamento usará esse provedor quando for executado.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-257">If there is, then the ReRoute will use that provider when it executes.</span></span>

<span data-ttu-id="bf8e1-258">Como o WebHost do Ocelot é configurado com o `authenticationProviderKey = "IdentityApiKey"`, ele exigirá a autenticação sempre que esse serviço tiver alguma solicitação sem nenhum token de autenticação.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-258">Because the Ocelot WebHost is configured with the `authenticationProviderKey = "IdentityApiKey"`, that will require authentication whenever that service has any requests without any auth token.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Startup
    {
        private readonly IConfiguration _cfg;

        public Startup(IConfiguration configuration) => _cfg = configuration;

        public void ConfigureServices(IServiceCollection services)
        {
            var identityUrl = _cfg.GetValue<string>("IdentityUrl");
            var authenticationProviderKey = "IdentityApiKey";
                         //…
            services.AddAuthentication()
                .AddJwtBearer(authenticationProviderKey, x =>
                {
                    x.Authority = identityUrl;
                    x.RequireHttpsMetadata = false;
                    x.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters()
                    {
                        ValidAudiences = new[] { "orders", "basket", "locations", "marketing", "mobileshoppingagg", "webshoppingagg" }
                    };
                });
            //...
        }
    }
}
```

<span data-ttu-id="bf8e1-259">Em seguida, você também precisará definir a autorização com o atributo [Authorize] nos recursos a serem acessados, como os microsserviços, como no seguinte controlador do microsserviço Cesta.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-259">Then, you also need to set authorization with the [Authorize] attribute on any resource to be accessed like the microservices, such as in the following Basket microservice controller.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class BasketController : Controller
    {
      //...
    }
}
```

<span data-ttu-id="bf8e1-260">O ValidAudiences, como "cesta", está correlacionado ao público definido em cada microserviço com `AddJwtBearer()` em configuraservices () da classe de inicialização, como no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-260">The ValidAudiences such as "basket" are correlated with the audience defined in each microservice with `AddJwtBearer()` at the ConfigureServices() of the Startup class, such as in the code below.</span></span>

```csharp
// prevent from mapping "sub" claim to nameidentifier.
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();

var identityUrl = Configuration.GetValue<string>("IdentityUrl");

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

}).AddJwtBearer(options =>
{
    options.Authority = identityUrl;
    options.RequireHttpsMetadata = false;
    options.Audience = "basket";
});
```

<span data-ttu-id="bf8e1-261">Se você tentar acessar qualquer microserviço protegido, como o microserviço da cesta com uma URL de redirecionamento com base no gateway de API como `http://localhost:5202/api/v1/b/basket/1` , você receberá um 401 não autorizado, a menos que forneça um token válido.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-261">If you try to access any secured microservice, like the Basket microservice with a ReRoute URL based on the API Gateway like `http://localhost:5202/api/v1/b/basket/1`, then you'll get a 401 Unauthorized unless you provide a valid token.</span></span> <span data-ttu-id="bf8e1-262">Por outro lado, se uma URL de redirecionamento for autenticada, o Ocelot invocará qualquer esquema downstream associado a ele (a URL interna de microatendimento).</span><span class="sxs-lookup"><span data-stu-id="bf8e1-262">On the other hand, if a ReRoute URL is authenticated, Ocelot will invoke whatever downstream scheme is associated with it (the internal microservice URL).</span></span>

<span data-ttu-id="bf8e1-263">**Autorização na camada de redirecionamentos do Ocelot.**</span><span class="sxs-lookup"><span data-stu-id="bf8e1-263">**Authorization at Ocelot's ReRoutes tier.**</span></span>  <span data-ttu-id="bf8e1-264">O Ocelot dá suporte a autorização baseada em declarações avaliada após a autenticação.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-264">Ocelot supports claims-based authorization evaluated after the authentication.</span></span> <span data-ttu-id="bf8e1-265">Defina a autorização em um nível de rota adicionando as linhas a seguir à configuração de Reencaminhamento.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-265">You set the authorization at a route level by adding the following lines to the ReRoute configuration.</span></span>

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

<span data-ttu-id="bf8e1-266">Nesse exemplo, quando o middleware de autorização for chamado, o Ocelot descobrirá se o usuário tem o tipo de declaração 'UserType' no token e se o valor dessa declaração é 'employee'.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-266">In that example, when the authorization middleware is called, Ocelot will find if the user has the claim type 'UserType' in the token and if the value of that claim is 'employee'.</span></span> <span data-ttu-id="bf8e1-267">Se não estiver, o usuário não será autorizado e a resposta será 403 Proibido.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-267">If it isn't, then the user will not be authorized and the response will be 403 forbidden.</span></span>

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a><span data-ttu-id="bf8e1-268">Usando a entrada do Kubernetes e os Gateways de API do Ocelot</span><span class="sxs-lookup"><span data-stu-id="bf8e1-268">Using Kubernetes Ingress plus Ocelot API Gateways</span></span>

<span data-ttu-id="bf8e1-269">Ao usar o kubernetes (como em um cluster do serviço kubernetes do Azure), você geralmente unificará todas as solicitações HTTP por meio da [camada de entrada do kubernetes](https://kubernetes.io/docs/concepts/services-networking/ingress/) com base em *Nginx*.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-269">When using Kubernetes (like in an Azure Kubernetes Service cluster), you usually unify all the HTTP requests through the [Kubernetes Ingress tier](https://kubernetes.io/docs/concepts/services-networking/ingress/) based on *Nginx*.</span></span>

<span data-ttu-id="bf8e1-270">No kubernetes, se você não usar nenhuma abordagem de entrada, seus serviços e pods terão IPs somente roteáveis pela rede de cluster.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-270">In Kubernetes, if you don't use any ingress approach, then your services and pods have IPs only routable by the cluster network.</span></span>

<span data-ttu-id="bf8e1-271">Mas se você usar uma abordagem de entrada, haverá uma camada intermediária entre a Internet e seus serviços (incluindo seus Gateways de API), atuando como um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-271">But if you use an ingress approach, you'll have a middle tier between the Internet and your services (including your API Gateways), acting as a reverse proxy.</span></span>

<span data-ttu-id="bf8e1-272">Como uma definição, uma entrada é uma coleção de regras que permitem que conexões de entrada acessem os serviços de cluster.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-272">As a definition, an Ingress is a collection of rules that allow inbound connections to reach the cluster services.</span></span> <span data-ttu-id="bf8e1-273">Uma entrada é configurada para fornecer aos serviços URLs acessadas externamente, balancear a carga do tráfego, terminação SSL e muito mais.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-273">An ingress is configured to provide services externally reachable URLs, load balance traffic, SSL termination and more.</span></span> <span data-ttu-id="bf8e1-274">Os usuários solicitam a entrada postando o recurso de entrada no servidor de API.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-274">Users request ingress by POSTing the Ingress resource to the API server.</span></span>

<span data-ttu-id="bf8e1-275">Em eShopOnContainers, ao desenvolver localmente e usar apenas o computador de desenvolvimento como o host do Docker, você não está usando nenhuma entrada, mas apenas vários Gateways de API.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-275">In eShopOnContainers, when developing locally and using just your development machine as the Docker host, you are not using any ingress but only the multiple API Gateways.</span></span>

<span data-ttu-id="bf8e1-276">No entanto, ao direcionar um ambiente de "produção" baseado em kubernetes, eShopOnContainers está usando uma entrada na frente dos gateways de API.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-276">However, when targeting a "production" environment based on Kubernetes, eShopOnContainers is using an ingress in front of the API gateways.</span></span> <span data-ttu-id="bf8e1-277">Dessa forma, os clientes ainda chamam a mesma URL base, mas as solicitações são encaminhadas para vários Gateways de API ou BFFs.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-277">That way, the clients still call the same base URL but the requests are routed to multiple API Gateways or BFF.</span></span>

<span data-ttu-id="bf8e1-278">Os gateways de API são front-ends ou as fachadas identificando apenas os serviços, mas não os aplicativos Web que normalmente estão fora de seu escopo.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-278">API Gateways are front-ends or façades surfacing only the services but not the web applications that are usually out of their scope.</span></span> <span data-ttu-id="bf8e1-279">Além disso, os Gateways de API podem ocultar determinados microsserviços internos.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-279">In addition, the API Gateways might hide certain internal microservices.</span></span>

<span data-ttu-id="bf8e1-280">A entrada, no entanto, está apenas redirecionando solicitações HTTP, mas não está tentando ocultar nenhum microsserviço ou aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-280">The ingress, however, is just redirecting HTTP requests but not trying to hide any microservice or web app.</span></span>

<span data-ttu-id="bf8e1-281">A arquitetura ideal é uma camada Nginx de entrada no Kubernetes na frente dos aplicativos Web além de vários Gateways de API/BFF do Ocelot, conforme é mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-281">Having an ingress Nginx tier in Kubernetes in front of the web applications plus the several Ocelot API Gateways / BFF is the ideal architecture, as shown in the following diagram.</span></span>

![Um diagrama que mostra como uma camada de entrada se encaixa no ambiente AKS.](./media/implement-api-gateways-with-ocelot/eshoponcontainer-ingress-tier.png)

<span data-ttu-id="bf8e1-283">**Figura 6-41**.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-283">**Figure 6-41**.</span></span> <span data-ttu-id="bf8e1-284">A camada de entrada em eShopOnContainers, quando implantada no Kubernetes</span><span class="sxs-lookup"><span data-stu-id="bf8e1-284">The ingress tier in eShopOnContainers when deployed into Kubernetes</span></span>

<span data-ttu-id="bf8e1-285">Uma entrada kubernetes atua como um proxy reverso para todo o tráfego para o aplicativo, incluindo os aplicativos Web, que estão fora do escopo do gateway de API.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-285">A Kubernetes Ingress acts as a reverse proxy for all traffic to the app, including the web applications, that are out of the Api gateway scope.</span></span> <span data-ttu-id="bf8e1-286">Quando você implanta o eShopOnContainers no Kubernetes, ele expõe apenas alguns serviços ou pontos de extremidade via _entrada_, ou seja, basicamente, a seguinte lista de pós-fixados nas URLs:</span><span class="sxs-lookup"><span data-stu-id="bf8e1-286">When you deploy eShopOnContainers into Kubernetes, it exposes just a few services or endpoints via _ingress_, basically the following list of postfixes on the URLs:</span></span>

- <span data-ttu-id="bf8e1-287">`/` para o aplicativo Web cliente SPA</span><span class="sxs-lookup"><span data-stu-id="bf8e1-287">`/` for the client SPA web application</span></span>
- <span data-ttu-id="bf8e1-288">`/webmvc` para o aplicativo Web cliente MVC</span><span class="sxs-lookup"><span data-stu-id="bf8e1-288">`/webmvc` for the client MVC web application</span></span>
- <span data-ttu-id="bf8e1-289">`/webstatus` para o aplicativo Web cliente mostrando o status e as verificações de integridade</span><span class="sxs-lookup"><span data-stu-id="bf8e1-289">`/webstatus` for the client web app showing the status/healthchecks</span></span>
- <span data-ttu-id="bf8e1-290">`/webshoppingapigw` para os processos de negócios Web BFF e de compras</span><span class="sxs-lookup"><span data-stu-id="bf8e1-290">`/webshoppingapigw` for the web BFF and shopping business processes</span></span>
- <span data-ttu-id="bf8e1-291">`/webmarketingapigw` para os processos de negócios Web BFF e de marketing</span><span class="sxs-lookup"><span data-stu-id="bf8e1-291">`/webmarketingapigw` for the web BFF and marketing business processes</span></span>
- <span data-ttu-id="bf8e1-292">`/mobileshoppingapigw` para os processos de negócios móveis BFF e de compras</span><span class="sxs-lookup"><span data-stu-id="bf8e1-292">`/mobileshoppingapigw` for the mobile BFF and shopping business processes</span></span>
- <span data-ttu-id="bf8e1-293">`/mobilemarketingapigw` para os processos de negócios móveis BFF e de marketing</span><span class="sxs-lookup"><span data-stu-id="bf8e1-293">`/mobilemarketingapigw` for the mobile BFF and marketing business processes</span></span>

<span data-ttu-id="bf8e1-294">Ao implantar no kubernetes, cada gateway de API do Ocelot está usando um arquivo "configuration.jsem" diferente para cada _Pod_ que executa os gateways de API.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-294">When deploying to Kubernetes, each Ocelot API Gateway is using a different "configuration.json" file for each _pod_ running the API Gateways.</span></span> <span data-ttu-id="bf8e1-295">Esses arquivos "configuration.jss" são fornecidos pela montagem (originalmente com o script deploy.ps1) de um volume criado com base em um _mapa de configuração_ kubernetes chamado ' Ocelot '.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-295">Those "configuration.json" files are provided by mounting (originally with the deploy.ps1 script) a volume created based on a Kubernetes _config map_ named ‘ocelot'.</span></span> <span data-ttu-id="bf8e1-296">Cada contêiner monta seu arquivo de configuração relacionado na pasta do contêiner chamada `/app/configuration` .</span><span class="sxs-lookup"><span data-stu-id="bf8e1-296">Each container mounts its related configuration file in the container's folder named `/app/configuration`.</span></span>

<span data-ttu-id="bf8e1-297">Nos arquivos de código-fonte do eShopOnContainers, os arquivos originais "configuration.jsem" podem ser encontrados na `k8s/ocelot/` pasta.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-297">In the source code files of eShopOnContainers, the original "configuration.json" files can be found within the `k8s/ocelot/` folder.</span></span> <span data-ttu-id="bf8e1-298">Há um arquivo para cada BFF/APIGateway.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-298">There's one file for each BFF/APIGateway.</span></span>

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a><span data-ttu-id="bf8e1-299">Recursos de interesses paralelos adicionais em um Gateway de API do Ocelot</span><span class="sxs-lookup"><span data-stu-id="bf8e1-299">Additional cross-cutting features in an Ocelot API Gateway</span></span>

<span data-ttu-id="bf8e1-300">Há outros recursos importantes que podem ser pesquisados e usados ao usar um Gateway de API do Ocelot, descritos nos links a seguir.</span><span class="sxs-lookup"><span data-stu-id="bf8e1-300">There are other important features to research and use, when using an Ocelot API Gateway, described in the following links.</span></span>

- <span data-ttu-id="bf8e1-301">**Descoberta de serviço no lado do cliente, integrando Ocelot com Consul ou Eureka** </span><span class="sxs-lookup"><span data-stu-id="bf8e1-301">**Service discovery in the client side integrating Ocelot with Consul or Eureka** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- <span data-ttu-id="bf8e1-302">**Caching na camada de gateway de API** </span><span class="sxs-lookup"><span data-stu-id="bf8e1-302">**Caching at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- <span data-ttu-id="bf8e1-303">**Registro em log na camada de gateway de API** </span><span class="sxs-lookup"><span data-stu-id="bf8e1-303">**Logging at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- <span data-ttu-id="bf8e1-304">**Qualidade de serviço (repetições e disjuntores de circuito) na camada de gateway de API** </span><span class="sxs-lookup"><span data-stu-id="bf8e1-304">**Quality of Service (Retries and Circuit breakers) at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- <span data-ttu-id="bf8e1-305">**Limitação de taxa** </span><span class="sxs-lookup"><span data-stu-id="bf8e1-305">**Rate limiting** </span></span>\
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> <span data-ttu-id="bf8e1-306">[Anterior](background-tasks-with-ihostedservice.md) 
>  [Avançar](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="bf8e1-306">[Previous](background-tasks-with-ihostedservice.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
