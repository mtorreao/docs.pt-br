---
title: Definindo o aplicativo de vários contêineres com o docker-compose.yml
description: Como especificar a composição de microsserviços para um aplicativo de vários contêineres com o docker-compose.yml.
ms.date: 01/30/2020
ms.openlocfilehash: 81303be621da54b7336228585e86d1120a6b7598
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739783"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="3089f-103">Definindo o aplicativo de vários contêineres com o docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="3089f-103">Defining your multi-container application with docker-compose.yml</span></span>

<span data-ttu-id="3089f-104">Neste guia, o arquivo [Docker-Compose. yml](https://docs.docker.com/compose/compose-file/) foi introduzido na seção [etapa 4. Defina seus serviços em Docker-Compose. yml ao criar um aplicativo Docker com vários contêineres](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span><span class="sxs-lookup"><span data-stu-id="3089f-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span></span> <span data-ttu-id="3089f-105">No entanto, há outras maneiras de usar os arquivos docker-compose e vale a pena explorá-las com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3089f-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="3089f-106">Por exemplo, você pode descrever explicitamente como deseja implantar o aplicativo de vários contêineres no arquivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="3089f-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="3089f-107">Opcionalmente, você também pode descrever como vai criar as imagens personalizadas do Docker.</span><span class="sxs-lookup"><span data-stu-id="3089f-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="3089f-108">(As imagens personalizadas do Docker também podem ser criadas com a CLI do Docker).</span><span class="sxs-lookup"><span data-stu-id="3089f-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="3089f-109">Basicamente, você define cada um dos contêineres que deseja implantar, além de determinadas características para cada implantação de contêiner.</span><span class="sxs-lookup"><span data-stu-id="3089f-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="3089f-110">Com um arquivo de descrição de implantação de vários contêineres pronto, você poderá implantar toda a solução por meio de uma única ação orquestrada pelo comando da CLI [docker-compose up](https://docs.docker.com/compose/overview/) ou poderá implantá-la de forma transparente no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3089f-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="3089f-111">Caso contrário, você precisará usar a CLI do Docker para implantar contêiner por contêiner, em várias etapas, usando o comando `docker run` na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3089f-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the `docker run` command from the command line.</span></span> <span data-ttu-id="3089f-112">Portanto, cada serviço definido no docker-compose.yml deve especificar exatamente uma imagem ou build.</span><span class="sxs-lookup"><span data-stu-id="3089f-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="3089f-113">As outras chaves são opcionais e são semelhantes aos correspondentes de `docker run` na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3089f-113">Other keys are optional, and are analogous to their `docker run` command-line counterparts.</span></span>

<span data-ttu-id="3089f-114">O código YAML a seguir é a definição de um arquivo docker-compose.yml possivelmente global, mas único, do exemplo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="3089f-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="3089f-115">Esse não é o verdadeiro arquivo docker-compose do eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="3089f-115">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="3089f-116">Em vez disso, ele é uma versão simplificada e consolidada em um único arquivo, o que não é a melhor maneira de se trabalhar com arquivos docker-compose, como será explicado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3089f-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '3.4'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
      - BasketUrl=http://basket-api
    ports:
      - "5100:80"
    depends_on:
      - catalog-api
      - ordering-api
      - basket-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=[PLACEHOLDER]
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=Services.OrderingDb;User Id=sa;Password=[PLACEHOLDER]
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  basket-api:
    image: eshop/basket-api
    environment:
      - ConnectionString=sqldata
    ports:
      - "5103:80"
    depends_on:
      - sqldata

  sqldata:
    environment:
      - SA_PASSWORD=[PLACEHOLDER]
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basketdata:
    image: redis
```

<span data-ttu-id="3089f-117">A chave de raiz desse arquivo é services.</span><span class="sxs-lookup"><span data-stu-id="3089f-117">The root key in this file is services.</span></span> <span data-ttu-id="3089f-118">Sob essa chave, você define os serviços que deseja implantar e executar ao executar o `docker-compose up` comando ou ao implantar a partir do Visual Studio usando esse arquivo Docker-Compose. yml.</span><span class="sxs-lookup"><span data-stu-id="3089f-118">Under that key, you define the services you want to deploy and run when you execute the `docker-compose up` command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="3089f-119">Nesse caso, o arquivo docker-compose.yml tem vários serviços definidos, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3089f-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following table.</span></span>

| <span data-ttu-id="3089f-120">Nome do serviço</span><span class="sxs-lookup"><span data-stu-id="3089f-120">Service name</span></span> | <span data-ttu-id="3089f-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="3089f-121">Description</span></span> |
|--------------|-------------|
| <span data-ttu-id="3089f-122">webmvc</span><span class="sxs-lookup"><span data-stu-id="3089f-122">webmvc</span></span>       | <span data-ttu-id="3089f-123">Contêiner, incluindo o aplicativo MVC ASP.NET Core, que consome os microsserviços do C\# do lado do servidor</span><span class="sxs-lookup"><span data-stu-id="3089f-123">Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>|
| <span data-ttu-id="3089f-124">Catálogo-API</span><span class="sxs-lookup"><span data-stu-id="3089f-124">catalog-api</span></span>  | <span data-ttu-id="3089f-125">Contêiner, incluindo o microsserviço de API Web do ASP.NET Core de Catálogo</span><span class="sxs-lookup"><span data-stu-id="3089f-125">Container including the Catalog ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="3089f-126">solicitação-API</span><span class="sxs-lookup"><span data-stu-id="3089f-126">ordering-api</span></span> | <span data-ttu-id="3089f-127">Contêiner, incluindo o microsserviço de API Web do ASP.NET Core de Pedidos</span><span class="sxs-lookup"><span data-stu-id="3089f-127">Container including the Ordering ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="3089f-128">SQLz</span><span class="sxs-lookup"><span data-stu-id="3089f-128">sqldata</span></span>     | <span data-ttu-id="3089f-129">Contêiner que executa o SQL Server para Linux armazenando os bancos de dados de microsserviços</span><span class="sxs-lookup"><span data-stu-id="3089f-129">Container running SQL Server for Linux, holding the microservices databases</span></span> |
| <span data-ttu-id="3089f-130">cesta-API</span><span class="sxs-lookup"><span data-stu-id="3089f-130">basket-api</span></span>   | <span data-ttu-id="3089f-131">Contêiner com o microsserviço de API Web do ASP.NET Core de Cesta</span><span class="sxs-lookup"><span data-stu-id="3089f-131">Container with the Basket ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="3089f-132">basketdata</span><span class="sxs-lookup"><span data-stu-id="3089f-132">basketdata</span></span>  | <span data-ttu-id="3089f-133">Contêiner que executa o serviço de Cache Redis, com o banco de dados da cesta como um Cache Redis</span><span class="sxs-lookup"><span data-stu-id="3089f-133">Container running the REDIS cache service, with the basket database as a REDIS cache</span></span> |

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="3089f-134">Um contêiner de API de serviço Web simples</span><span class="sxs-lookup"><span data-stu-id="3089f-134">A simple Web Service API container</span></span>

<span data-ttu-id="3089f-135">Concentrando-se em um único contêiner, o contêiner Catalog-API-Microservice tem uma definição simples:</span><span class="sxs-lookup"><span data-stu-id="3089f-135">Focusing on a single container, the catalog-api container-microservice has a straightforward definition:</span></span>

```yml
  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=[PLACEHOLDER]
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata
```

<span data-ttu-id="3089f-136">Esse serviço em contêiner tem a seguinte configuração básica:</span><span class="sxs-lookup"><span data-stu-id="3089f-136">This containerized service has the following basic configuration:</span></span>

- <span data-ttu-id="3089f-137">Ele se baseia na imagem personalizada do **eshop/Catalog-API** .</span><span class="sxs-lookup"><span data-stu-id="3089f-137">It is based on the custom **eshop/catalog-api** image.</span></span> <span data-ttu-id="3089f-138">Para simplificar, não há nenhuma configuração Build: Key no arquivo.</span><span class="sxs-lookup"><span data-stu-id="3089f-138">For simplicity's sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="3089f-139">Isso significa que a imagem deverá ser previamente compilada (com docker build) ou ser baixada (com o comando docker pull) de qualquer registro do Docker.</span><span class="sxs-lookup"><span data-stu-id="3089f-139">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

- <span data-ttu-id="3089f-140">Ele define uma variável de ambiente denominada ConnectionString, com a cadeia de conexão a ser usada pelo Entity Framework para acessar a instância do SQL Server que contém o modelo de dados de catálogo.</span><span class="sxs-lookup"><span data-stu-id="3089f-140">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="3089f-141">Nesse caso, o mesmo contêiner do SQL Server está mantendo vários bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3089f-141">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="3089f-142">Dessa forma, você precisará de menos memória no computador de desenvolvimento do Docker.</span><span class="sxs-lookup"><span data-stu-id="3089f-142">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="3089f-143">No entanto, você também poderia implantar um contêiner do SQL Server para cada banco de dados de microsserviço.</span><span class="sxs-lookup"><span data-stu-id="3089f-143">However, you could also deploy one SQL Server container for each microservice database.</span></span>

- <span data-ttu-id="3089f-144">O nome do SQL Server é **SQLdata**, que é o mesmo nome usado para o contêiner que está executando a instância de SQL Server para Linux.</span><span class="sxs-lookup"><span data-stu-id="3089f-144">The SQL Server name is **sqldata**, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="3089f-145">Isso é conveniente; a possibilidade de usar essa resolução de nome (interna ao host do Docker) resolverá o endereço de rede para que você não precise saber o IP interno dos contêineres que você está acessando de outros contêineres.</span><span class="sxs-lookup"><span data-stu-id="3089f-145">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don't need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="3089f-146">Como a cadeia de conexão é definida por uma variável de ambiente, você pode definir essa variável por meio de um mecanismo diferente e em outro momento.</span><span class="sxs-lookup"><span data-stu-id="3089f-146">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="3089f-147">Por exemplo, você pode definir uma cadeia de conexão diferente durante a implantação em produção nos hosts finais ou fazer isso através dos pipelines de CI/CD no Azure DevOps Services ou no sistema de DevOps de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="3089f-147">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in Azure DevOps Services or your preferred DevOps system.</span></span>

- <span data-ttu-id="3089f-148">Ele expõe a porta 80 para acesso interno ao serviço de **API de catálogo** no host do Docker.</span><span class="sxs-lookup"><span data-stu-id="3089f-148">It exposes port 80 for internal access to the **catalog-api** service within the Docker host.</span></span> <span data-ttu-id="3089f-149">Atualmente o host é uma VM do Linux, porque ele se baseia em uma imagem do Docker para Linux, mas você também pode configurar o contêiner para ser executado em uma imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="3089f-149">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

- <span data-ttu-id="3089f-150">Ele encaminha a porta 80, exposta no contêiner, para a porta 5101 no computador host do Docker (a VM do Linux).</span><span class="sxs-lookup"><span data-stu-id="3089f-150">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

- <span data-ttu-id="3089f-151">Ele vincula o serviço Web ao serviço **SQLdata** (a instância de SQL Server para o banco de dados do Linux em execução em um contêiner).</span><span class="sxs-lookup"><span data-stu-id="3089f-151">It links the web service to the **sqldata** service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="3089f-152">Quando você especificar essa dependência, o contêiner Catalog-API não será iniciado até que o contêiner SQLdata já tenha começado; Isso é importante porque o Catalog-API precisa ter o banco de dados do SQL Server em execução primeiro.</span><span class="sxs-lookup"><span data-stu-id="3089f-152">When you specify this dependency, the catalog-api container will not start until the sqldata container has already started; this is important because catalog-api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="3089f-153">No entanto, esse tipo de dependência de contêiner não é suficiente em muitos casos, porque o Docker verifica apenas no nível de contêiner.</span><span class="sxs-lookup"><span data-stu-id="3089f-153">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="3089f-154">Às vezes, o serviço (o SQL Server, neste caso) poderá ainda não estar pronto, portanto, é aconselhável implementar uma lógica de repetição com retirada exponencial no microsserviço cliente.</span><span class="sxs-lookup"><span data-stu-id="3089f-154">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="3089f-155">Dessa forma, se um contêiner de dependência não estiver pronto durante um breve período de tempo, o aplicativo continuará resiliente.</span><span class="sxs-lookup"><span data-stu-id="3089f-155">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

- <span data-ttu-id="3089f-156">Ele está configurado para permitir o acesso a servidores externos: a \_ configuração hosts extras permite que você acesse servidores externos ou computadores fora do host do Docker (ou seja, fora da VM do Linux padrão, que é um host do Docker de desenvolvimento), como uma instância de SQL Server local no seu PC de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="3089f-156">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM, which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="3089f-157">Também há outras configurações mais avançadas `docker-compose.yml` que discutiremos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="3089f-157">There are also other, more advanced `docker-compose.yml` settings that we'll discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="3089f-158">Usando arquivos docker-compose para destinar-se a vários ambientes</span><span class="sxs-lookup"><span data-stu-id="3089f-158">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="3089f-159">Os `docker-compose.*.yml` arquivos são arquivos de definição e podem ser usados por várias infraestruturas que entendem esse formato.</span><span class="sxs-lookup"><span data-stu-id="3089f-159">The `docker-compose.*.yml` files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="3089f-160">A ferramenta mais simples é o comando docker-compose.</span><span class="sxs-lookup"><span data-stu-id="3089f-160">The most straightforward tool is the docker-compose command.</span></span>

<span data-ttu-id="3089f-161">Portanto, ao usar o comando docker-compose você pode ter os seguintes principais cenários como destino.</span><span class="sxs-lookup"><span data-stu-id="3089f-161">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="3089f-162">Ambientes de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="3089f-162">Development environments</span></span>

<span data-ttu-id="3089f-163">Ao desenvolver aplicativos, é importante ser capaz de executar um aplicativo em um ambiente de desenvolvimento isolado.</span><span class="sxs-lookup"><span data-stu-id="3089f-163">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="3089f-164">Você pode usar o comando Docker-Compose CLI para criar esse ambiente ou o Visual Studio, que usa o Docker-Compose nos bastidores.</span><span class="sxs-lookup"><span data-stu-id="3089f-164">You can use the docker-compose CLI command to create that environment or Visual Studio, which uses docker-compose under the covers.</span></span>

<span data-ttu-id="3089f-165">O arquivo Docker-Compose. yml permite que você configure e documente todas as dependências de serviço do seu aplicativo (outros serviços, cache, bancos de dados, filas, etc.).</span><span class="sxs-lookup"><span data-stu-id="3089f-165">The docker-compose.yml file allows you to configure and document all your application's service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="3089f-166">Ao usar o comando de CLI docker-compose, você pode criar e iniciar um ou mais contêineres para cada dependência com um único comando (docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="3089f-166">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="3089f-167">Os docker-compose.yml são arquivos de configuração interpretados pelo mecanismo do Docker, mas também servem como arquivos de documentação convenientes, com informações sobre a composição de seu aplicativo para vários contêineres.</span><span class="sxs-lookup"><span data-stu-id="3089f-167">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="3089f-168">Ambientes de teste</span><span class="sxs-lookup"><span data-stu-id="3089f-168">Testing environments</span></span>

<span data-ttu-id="3089f-169">Uma parte importante de qualquer processo de CD (implantação contínua) ou CI (integração contínua) são os testes de unidade e testes de integração.</span><span class="sxs-lookup"><span data-stu-id="3089f-169">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="3089f-170">Esses testes automatizados exigem um ambiente isolado para que não sejam afetados pelos usuários ou por qualquer outra alteração nos dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3089f-170">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application's data.</span></span>

<span data-ttu-id="3089f-171">Com o Docker Compose, você pode criar e destruir esse ambiente isolado com muito facilidade em alguns comandos do prompt de comando ou scripts, como os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="3089f-171">With Docker Compose, you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml up -d
./run_unit_tests
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml down
```

#### <a name="production-deployments"></a><span data-ttu-id="3089f-172">Implantações de produção</span><span class="sxs-lookup"><span data-stu-id="3089f-172">Production deployments</span></span>

<span data-ttu-id="3089f-173">Você também pode usar o Compose para implantar em um mecanismo remoto do Docker.</span><span class="sxs-lookup"><span data-stu-id="3089f-173">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="3089f-174">Um caso comum é a implantação em uma única instância de host do Docker (como uma VM ou servidor de produção, provisionados com o [Docker Machine](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="3089f-174">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span>

<span data-ttu-id="3089f-175">Se estiver usando qualquer outro orquestrador (Azure Service Fabric, Kubernetes, etc.), precisará adicionar definições de configuração de instalação e metadados, como aquelas em docker-compose.yml, mas no formato exigido pelo outro orquestrador.</span><span class="sxs-lookup"><span data-stu-id="3089f-175">If you are using any other orchestrator (Azure Service Fabric, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="3089f-176">De qualquer maneira, o docker-compose é uma ferramenta conveniente e um formato de metadados para fluxos de trabalho de desenvolvimento, teste e produção, embora o fluxo de trabalho de produção possa variar no orquestrador que você está usando.</span><span class="sxs-lookup"><span data-stu-id="3089f-176">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="3089f-177">Usando vários arquivos docker-compose para lidar com diversos ambientes</span><span class="sxs-lookup"><span data-stu-id="3089f-177">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="3089f-178">Ao destinar-se a ambientes diferentes, você deve usar vários arquivos compose.</span><span class="sxs-lookup"><span data-stu-id="3089f-178">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="3089f-179">Isso permite que você crie diversas variantes de configuração, dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="3089f-179">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="3089f-180">Substituindo o arquivo base docker-compose</span><span class="sxs-lookup"><span data-stu-id="3089f-180">Overriding the base docker-compose file</span></span>

<span data-ttu-id="3089f-181">Você pode usar um único arquivo docker-compose.yml, como nos exemplos simplificados mostrados nas seções anteriores.</span><span class="sxs-lookup"><span data-stu-id="3089f-181">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="3089f-182">No entanto, isso não é recomendável para a maioria dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3089f-182">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="3089f-183">Por padrão, o Compose lê dois arquivos, um docker-compose.yml e um arquivo docker-compose.override.yml opcional.</span><span class="sxs-lookup"><span data-stu-id="3089f-183">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="3089f-184">Conforme mostrado na Figura 6-11, quando você estiver usando o Visual Studio e habilitar o suporte ao Docker, o Visual Studio também criará um arquivo docker-compose.vs.debug.g.yml adicional para depurar o aplicativo. Dê uma olhada nesse arquivo na pasta obj\\Docker\\ da pasta da solução principal.</span><span class="sxs-lookup"><span data-stu-id="3089f-184">As shown in Figure 6-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.vs.debug.g.yml file for debugging the application, you can take a look at this file in folder obj\\Docker\\ in the main solution folder.</span></span>

![Arquivos em um projeto do Docker Compose.](./media/multi-container-applications-docker-compose/docker-compose-file-visual-studio.png)

<span data-ttu-id="3089f-186">**Figura 6-11**.</span><span class="sxs-lookup"><span data-stu-id="3089f-186">**Figure 6-11**.</span></span> <span data-ttu-id="3089f-187">arquivos Docker-Compose no Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3089f-187">docker-compose files in Visual Studio 2019</span></span>

<span data-ttu-id="3089f-188">estrutura do arquivo de projeto do **Docker-Compose** :</span><span class="sxs-lookup"><span data-stu-id="3089f-188">**docker-compose** project file structure:</span></span>

- <span data-ttu-id="3089f-189">*. dockerignore* -usado para ignorar arquivos</span><span class="sxs-lookup"><span data-stu-id="3089f-189">*.dockerignore* - used to ignore files</span></span>
- <span data-ttu-id="3089f-190">*Docker-Compose. yml* -usado para compor microserviços</span><span class="sxs-lookup"><span data-stu-id="3089f-190">*docker-compose.yml* - used to compose microservices</span></span>
- <span data-ttu-id="3089f-191">*Docker-Compose. Override. yml* -usado para configurar o ambiente de microserviços</span><span class="sxs-lookup"><span data-stu-id="3089f-191">*docker-compose.override.yml* - used to configure microservices environment</span></span>

<span data-ttu-id="3089f-192">Você pode editar os arquivos docker-compose com qualquer editor, como o Visual Studio Code ou o Sublime, e executar o aplicativo com o comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="3089f-192">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="3089f-193">Por convenção, o arquivo docker-compose.yml contém sua configuração base e outras configurações estáticas.</span><span class="sxs-lookup"><span data-stu-id="3089f-193">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="3089f-194">Isso significa que a configuração do serviço não deve ser alterada de acordo com o ambiente de implantação que você tem como destino.</span><span class="sxs-lookup"><span data-stu-id="3089f-194">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="3089f-195">O arquivo docker-compose.override.yml, como o próprio nome sugere, contém definições de configuração que substituem a configuração base, como a configuração que depende do ambiente de implantação.</span><span class="sxs-lookup"><span data-stu-id="3089f-195">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="3089f-196">Você também pode ter vários arquivos de substituição com nomes diferentes.</span><span class="sxs-lookup"><span data-stu-id="3089f-196">You can have multiple override files with different names also.</span></span> <span data-ttu-id="3089f-197">Os arquivos de substituição geralmente contêm informações adicionais, exigidas pelo aplicativo, bem como as informações específicas de um ambiente ou uma implantação.</span><span class="sxs-lookup"><span data-stu-id="3089f-197">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="3089f-198">Destinando-se a vários ambientes</span><span class="sxs-lookup"><span data-stu-id="3089f-198">Targeting multiple environments</span></span>

<span data-ttu-id="3089f-199">Um caso de uso típico é aquele em que você define vários arquivos compose para destinar-se a vários ambientes, como de produção, de preparo, de CI ou de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="3089f-199">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="3089f-200">Para dar suporte a essas diferenças, você pode dividir a configuração do Compose em vários arquivos, conforme mostrado na Figura 6-12.</span><span class="sxs-lookup"><span data-stu-id="3089f-200">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 6-12.</span></span>

![Diagrama de três arquivos Docker-Compose definidos para substituir o arquivo base.](./media/multi-container-applications-docker-compose/multiple-docker-compose-files-override-base.png)

<span data-ttu-id="3089f-202">**Figura 6-12**.</span><span class="sxs-lookup"><span data-stu-id="3089f-202">**Figure 6-12**.</span></span> <span data-ttu-id="3089f-203">Vários arquivos docker-compose substituindo valores no arquivo base docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="3089f-203">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="3089f-204">Você pode combinar vários arquivos Docker-Compose\*. yml para lidar com ambientes diferentes.</span><span class="sxs-lookup"><span data-stu-id="3089f-204">You can combine multiple docker-compose\*.yml files to handle different environments.</span></span> <span data-ttu-id="3089f-205">Você inicia com o arquivo base docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="3089f-205">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="3089f-206">Esse arquivo base contém as definições de configuração básica ou estática que não são alteradas dependendo do ambiente.</span><span class="sxs-lookup"><span data-stu-id="3089f-206">This base file contains the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="3089f-207">Por exemplo, o aplicativo eShopOnContainers tem o seguinte arquivo Docker-Compose. yml (simplificado com menos serviços) que o arquivo base.</span><span class="sxs-lookup"><span data-stu-id="3089f-207">For example, the eShopOnContainers app has the following docker-compose.yml file (simplified with fewer services) as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '3.4'
services:
  basket-api:
    image: eshop/basket-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Basket/Basket.API/Dockerfile
    depends_on:
      - basketdata
      - identity-api
      - rabbitmq

  catalog-api:
    image: eshop/catalog-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Catalog/Catalog.API/Dockerfile
    depends_on:
      - sqldata
      - rabbitmq

  marketing-api:
    image: eshop/marketing-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Marketing/Marketing.API/Dockerfile
    depends_on:
      - sqldata
      - nosqldata
      - identity-api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Web/WebMVC/Dockerfile
    depends_on:
      - catalog-api
      - ordering-api
      - identity-api
      - basket-api
      - marketing-api

  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest

  nosqldata:
    image: mongo

  basketdata:
    image: redis

  rabbitmq:
    image: rabbitmq:3-management

```

<span data-ttu-id="3089f-208">Os valores do arquivo base docker-compose.yml não devem se alterar devido aos diferentes ambientes de implantação de destino.</span><span class="sxs-lookup"><span data-stu-id="3089f-208">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="3089f-209">Se você se concentrar na definição do serviço webmvc, por exemplo, verá como essa informação é muito semelhante independentemente do ambiente ao qual você se destina.</span><span class="sxs-lookup"><span data-stu-id="3089f-209">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="3089f-210">Você tem as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3089f-210">You have the following information:</span></span>

- <span data-ttu-id="3089f-211">O nome do serviço: webmvc.</span><span class="sxs-lookup"><span data-stu-id="3089f-211">The service name: webmvc.</span></span>

- <span data-ttu-id="3089f-212">A imagem personalizada do contêiner: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="3089f-212">The container's custom image: eshop/webmvc.</span></span>

- <span data-ttu-id="3089f-213">O comando para compilar a imagem personalizada do Docker, que indica qual Dockerfile usar.</span><span class="sxs-lookup"><span data-stu-id="3089f-213">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

- <span data-ttu-id="3089f-214">As dependências de outros serviços, para que este contêiner não se inicie até que os outros contêineres de dependência sejam iniciados.</span><span class="sxs-lookup"><span data-stu-id="3089f-214">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="3089f-215">Você pode ter outras configurações, mas o ponto importante é que, no arquivo base docker-compose.yml, é necessário definir apenas as informações que são comuns entre ambientes.</span><span class="sxs-lookup"><span data-stu-id="3089f-215">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="3089f-216">Então, no docker-compose.override.yml ou em arquivos semelhantes de produção ou de preparo, você deve colocar a configuração específica para cada ambiente.</span><span class="sxs-lookup"><span data-stu-id="3089f-216">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="3089f-217">Normalmente, o docker-compose.override.yml é usado para o ambiente de desenvolvimento, como no exemplo a seguir, do eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="3089f-217">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3.4'

services:
# Simplified number of services here:

  basket-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basketdata}
      - identityUrl=http://identity-api
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=[PLACEHOLDER]}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5202/api/v1/catalog/items/[0]/pic/}
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=[PLACEHOLDER]}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - identityUrl=http://identity-api
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - PurchaseUrl=http://webshoppingapigw
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://webmarketingapigw
      - CatalogUrlHC=http://catalog-api/hc
      - OrderingUrlHC=http://ordering-api/hc
      - IdentityUrlHC=http://identity-api/hc
      - BasketUrlHC=http://basket-api/hc
      - MarketingUrlHC=http://marketing-api/hc
      - PaymentUrlHC=http://payment-api/hc
      - SignalrHubUrl=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5202
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sqldata:
    environment:
      - SA_PASSWORD=[PLACEHOLDER]
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
  basketdata:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

<span data-ttu-id="3089f-218">Neste exemplo, a configuração de substituição de desenvolvimento expõe algumas portas para o host, define variáveis de ambiente com URLs de redirecionamento e especifica cadeias de conexão para o ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="3089f-218">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="3089f-219">Todas essas configurações são apenas para o ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="3089f-219">These settings are all just for the development environment.</span></span>

<span data-ttu-id="3089f-220">Quando você executa `docker-compose up` (ou o inicia no Visual Studio), o comando lerá as substituições automaticamente como se estivesse mesclando os dois arquivos.</span><span class="sxs-lookup"><span data-stu-id="3089f-220">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="3089f-221">Suponha que você deseja outro arquivo de composição para o ambiente de produção, com valores de configuração, portas ou cadeias de conexão diferentes.</span><span class="sxs-lookup"><span data-stu-id="3089f-221">Suppose that you want another Compose file for the production environment, with different configuration values, ports, or connection strings.</span></span> <span data-ttu-id="3089f-222">Você pode criar outro arquivo de substituição, como um arquivo chamado `docker-compose.prod.yml`, com diferentes configurações e variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="3089f-222">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span> <span data-ttu-id="3089f-223">Esse arquivo poderá ser armazenado em outro repositório GIT ou gerenciado e protegido por uma equipe diferente.</span><span class="sxs-lookup"><span data-stu-id="3089f-223">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="3089f-224">Como implantar com um arquivo de substituição específico</span><span class="sxs-lookup"><span data-stu-id="3089f-224">How to deploy with a specific override file</span></span>

<span data-ttu-id="3089f-225">Para usar vários arquivos de substituição, ou um arquivo de substituição com um nome diferente, use a opção -f com o comando docker-compose e especifique os arquivos.</span><span class="sxs-lookup"><span data-stu-id="3089f-225">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="3089f-226">O Compose mescla os arquivos na ordem em que eles são especificados na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3089f-226">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="3089f-227">O exemplo a seguir mostra como implantar com arquivos de substituição.</span><span class="sxs-lookup"><span data-stu-id="3089f-227">The following example shows how to deploy with override files.</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="3089f-228">Usando variáveis de ambiente em arquivos docker-compose</span><span class="sxs-lookup"><span data-stu-id="3089f-228">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="3089f-229">É conveniente, especialmente em ambientes de produção, ter a possibilidade de obter informações de configuração de variáveis de ambiente, como mostramos em exemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="3089f-229">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="3089f-230">Referencie uma variável de ambiente nos arquivos docker-compose usando a sintaxe ${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="3089f-230">You can reference an environment variable in your docker-compose files using the syntax ${MY\_VAR}.</span></span> <span data-ttu-id="3089f-231">A seguinte linha de um arquivo docker-compose.prod.yml mostra como referenciar o valor de uma variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="3089f-231">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="3089f-232">As variáveis de ambiente são criadas e inicializadas de diferentes maneiras, dependendo do ambiente de host (Linux, Windows, cluster de nuvem, etc.).</span><span class="sxs-lookup"><span data-stu-id="3089f-232">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="3089f-233">Entretanto, uma abordagem conveniente é usar um arquivo .env.</span><span class="sxs-lookup"><span data-stu-id="3089f-233">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="3089f-234">Os arquivos docker-compose são compatíveis com a declaração de variáveis de ambiente padrão no arquivo .env.</span><span class="sxs-lookup"><span data-stu-id="3089f-234">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="3089f-235">Esses valores das variáveis de ambiente são os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="3089f-235">These values for the environment variables are the default values.</span></span> <span data-ttu-id="3089f-236">Mas elas podem ser substituídas pelos valores que você definiu em cada um dos ambientes (sistema operacional de host ou variáveis de ambiente do cluster).</span><span class="sxs-lookup"><span data-stu-id="3089f-236">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="3089f-237">Coloque esse arquivo .env na pasta em que o comando docker-compose é executado.</span><span class="sxs-lookup"><span data-stu-id="3089f-237">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="3089f-238">O exemplo a seguir mostra um arquivo .env parecido com o [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) do aplicativo eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="3089f-238">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```sh
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="3089f-239">O Docker-Compose espera que cada linha em um arquivo. env esteja no formato \<variable\> = \<value\> .</span><span class="sxs-lookup"><span data-stu-id="3089f-239">Docker-compose expects each line in an .env file to be in the format \<variable\>=\<value\>.</span></span>

<span data-ttu-id="3089f-240">Os valores definidos no ambiente de tempo de execução sempre substituem os valores definidos dentro do arquivo. env.</span><span class="sxs-lookup"><span data-stu-id="3089f-240">The values set in the run-time environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="3089f-241">De forma semelhante, os valores passados por meio de argumentos de linha de comando também substituem os valores padrão definidos no arquivo. env.</span><span class="sxs-lookup"><span data-stu-id="3089f-241">In a similar way, values passed via command-line arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="3089f-242">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3089f-242">Additional resources</span></span>

- <span data-ttu-id="3089f-243">**Visão geral do Docker Compose** </span><span class="sxs-lookup"><span data-stu-id="3089f-243">**Overview of Docker Compose** </span></span>\
    <https://docs.docker.com/compose/overview/>

- <span data-ttu-id="3089f-244">**Vários arquivos de composição** </span><span class="sxs-lookup"><span data-stu-id="3089f-244">**Multiple Compose files** </span></span>\
    [https://docs.docker.com/compose/extends/\#multiple-compose-files](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="3089f-245">Criando imagens do Docker do ASP.NET Core otimizadas</span><span class="sxs-lookup"><span data-stu-id="3089f-245">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="3089f-246">Se estiver explorando o Docker e o .NET Core em fontes na Internet, você encontrará Dockerfiles que demonstram a simplicidade da criação de uma imagem do Docker por meio da cópia da fonte em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="3089f-246">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="3089f-247">Esses exemplos sugerem que, ao usar uma configuração simples, você pode ter uma imagem do Docker com o ambiente empacotado com seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3089f-247">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="3089f-248">O exemplo a seguir mostra um Dockerfile simples neste sentido.</span><span class="sxs-lookup"><span data-stu-id="3089f-248">The following example shows a simple Dockerfile in this vein.</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:3.1
WORKDIR /app
ENV ASPNETCORE_URLS http://+:80
EXPOSE 80
COPY . .
RUN dotnet restore
ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="3089f-249">Um Dockerfile como esse funcionará.</span><span class="sxs-lookup"><span data-stu-id="3089f-249">A Dockerfile like this will work.</span></span> <span data-ttu-id="3089f-250">No entanto, você pode otimizar substancialmente suas imagens, especialmente as imagens de produção.</span><span class="sxs-lookup"><span data-stu-id="3089f-250">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="3089f-251">No modelo de contêiner e microsserviços, você está constantemente iniciando contêineres.</span><span class="sxs-lookup"><span data-stu-id="3089f-251">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="3089f-252">O modo comum de uso de contêineres não reinicia um contêiner em suspensão porque o contêiner é descartável.</span><span class="sxs-lookup"><span data-stu-id="3089f-252">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="3089f-253">Orquestradores (como o Kubernetes e o Azure Service Fabric) simplesmente criam instâncias de imagens.</span><span class="sxs-lookup"><span data-stu-id="3089f-253">Orchestrators (like Kubernetes and Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="3089f-254">Isso significa que você precisará otimizar por meio da pré-compilação do aplicativo quando ele for criado, fazendo com que o processo de instanciação seja mais rápido.</span><span class="sxs-lookup"><span data-stu-id="3089f-254">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="3089f-255">Quando o contêiner é iniciado, ele deve estar pronto para executar.</span><span class="sxs-lookup"><span data-stu-id="3089f-255">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="3089f-256">Não restaure e compile em tempo de execução usando `dotnet restore` os `dotnet build` comandos da CLI e como você pode ver em Postagens de blog sobre o .NET Core e o Docker.</span><span class="sxs-lookup"><span data-stu-id="3089f-256">Don't restore and compile at run time using the `dotnet restore` and `dotnet build` CLI commands as you may see in blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="3089f-257">A equipe do .NET está realizando um trabalho importante para tornar o .NET Core e o ASP.NET Core uma estrutura otimizada para contêineres.</span><span class="sxs-lookup"><span data-stu-id="3089f-257">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="3089f-258">O .NET Core não é apenas uma estrutura leve com um volume de memória pequeno; a equipe se concentrou em imagens do Docker otimizadas para três cenários principais e as publicou no Registro no Hub do Docker em *dotnet/core*, começando na versão 2.1:</span><span class="sxs-lookup"><span data-stu-id="3089f-258">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on optimized Docker images for three main scenarios and published them in the Docker Hub registry at *dotnet/core*, beginning with version 2.1:</span></span>

1. <span data-ttu-id="3089f-259">**Desenvolvimento**: a prioridade é a capacidade de iterar e depurar rapidamente as alterações, e onde o tamanho é secundário.</span><span class="sxs-lookup"><span data-stu-id="3089f-259">**Development**: The priority is the ability to quickly iterate and debug changes, and where size is secondary.</span></span>

2. <span data-ttu-id="3089f-260">**Compilação**: a prioridade está compilando o aplicativo e a imagem inclui binários e outras dependências para otimizar os binários.</span><span class="sxs-lookup"><span data-stu-id="3089f-260">**Build**: The priority is compiling the application, and the image includes binaries and other dependencies to optimize binaries.</span></span>

3. <span data-ttu-id="3089f-261">**Produção**: o foco é a implantação rápida e a inicialização de contêineres, portanto, essas imagens são limitadas aos binários e ao conteúdo necessário para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3089f-261">**Production**: The focus is fast deploying and starting of containers, so these images are limited to the binaries and content needed to run the application.</span></span>

<span data-ttu-id="3089f-262">A equipe do .NET fornece quatro variantes básicas no [dotnet/núcleo](https://hub.docker.com/_/microsoft-dotnet/) (no Hub do Docker):</span><span class="sxs-lookup"><span data-stu-id="3089f-262">The .NET team provides four basic variants in [dotnet/core](https://hub.docker.com/_/microsoft-dotnet/) (at Docker Hub):</span></span>

1. <span data-ttu-id="3089f-263">**sdk**: para cenários de desenvolvimento e build</span><span class="sxs-lookup"><span data-stu-id="3089f-263">**sdk**: for development and build scenarios</span></span>
1. <span data-ttu-id="3089f-264">**aspnet**: para cenários de produção do ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3089f-264">**aspnet**: for ASP.NET production scenarios</span></span>
1. <span data-ttu-id="3089f-265">**runtime**: para cenários de produção do .NET</span><span class="sxs-lookup"><span data-stu-id="3089f-265">**runtime**: for .NET production scenarios</span></span>
1. <span data-ttu-id="3089f-266">**tempo de execução-deps**: para cenários de produção de [aplicativos](../../../core/deploying/index.md#publish-self-contained) independentes</span><span class="sxs-lookup"><span data-stu-id="3089f-266">**runtime-deps**: for production scenarios of [self-contained applications](../../../core/deploying/index.md#publish-self-contained)</span></span>

<span data-ttu-id="3089f-267">Para uma inicialização mais rápida, as imagens de runtime também definem automaticamente aspnetcore\_urls para a porta 80 e usam o Ngen para criar um cache de imagens nativas de assemblies.</span><span class="sxs-lookup"><span data-stu-id="3089f-267">For faster startup, runtime images also automatically set aspnetcore\_urls to port 80 and use Ngen to create a native image cache of assemblies.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="3089f-268">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3089f-268">Additional resources</span></span>

- <span data-ttu-id="3089f-269">**Criando imagens otimizadas do Docker com ASP.NET Core**
  <https://docs.microsoft.com/archive/blogs/stevelasker/building-optimized-docker-images-with-asp-net-core></span><span class="sxs-lookup"><span data-stu-id="3089f-269">**Building Optimized Docker Images with ASP.NET Core**
<https://docs.microsoft.com/archive/blogs/stevelasker/building-optimized-docker-images-with-asp-net-core></span></span>

- <span data-ttu-id="3089f-270">**Criando imagens do Docker para aplicativos .NET Core**
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)</span><span class="sxs-lookup"><span data-stu-id="3089f-270">**Building Docker Images for .NET Core Applications**
[https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="3089f-271">[Anterior](data-driven-crud-microservice.md) 
>  [Avançar](database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="3089f-271">[Previous](data-driven-crud-microservice.md)
[Next](database-server-container.md)</span></span>
