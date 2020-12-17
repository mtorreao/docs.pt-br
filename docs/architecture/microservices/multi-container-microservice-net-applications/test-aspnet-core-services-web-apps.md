---
title: Testar serviços e aplicativos Web do ASP.NET Core
description: Arquitetura de microsserviços do .NET para aplicativos .NET em contêineres | Explorar uma arquitetura para testar serviços e aplicativos Web do ASP.NET Core em contêineres.
ms.date: 08/07/2020
ms.openlocfilehash: 67872668781d8ae5d79bf360aee73f744cf4404b
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633943"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="ba204-103">Testar serviços e aplicativos Web do ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ba204-103">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="ba204-104">Os controladores são uma parte central de qualquer serviço de API do ASP.NET Core e aplicativo Web ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="ba204-104">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="ba204-105">Assim, você precisa estar confiante de que eles se comportarão conforme o esperado para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ba204-105">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="ba204-106">Testes automatizados podem fornecer essa confiança e detectar erros antes que eles atinjam a produção.</span><span class="sxs-lookup"><span data-stu-id="ba204-106">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="ba204-107">É necessário testar como o controlador se comporta com base em entradas válidas ou inválidas, bem como testar suas respostas com base nos resultados da operação de negócios realizada.</span><span class="sxs-lookup"><span data-stu-id="ba204-107">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="ba204-108">No entanto, você deveria ter esses tipos de testes nos seus microsserviços:</span><span class="sxs-lookup"><span data-stu-id="ba204-108">However, you should have these types of tests for your microservices:</span></span>

- <span data-ttu-id="ba204-109">Testes de unidade.</span><span class="sxs-lookup"><span data-stu-id="ba204-109">Unit tests.</span></span> <span data-ttu-id="ba204-110">Eles garantem que os componentes individuais do aplicativo funcionam como esperado.</span><span class="sxs-lookup"><span data-stu-id="ba204-110">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="ba204-111">Instruções assert testam a API do componente.</span><span class="sxs-lookup"><span data-stu-id="ba204-111">Assertions test the component API.</span></span>

- <span data-ttu-id="ba204-112">Testes de integração.</span><span class="sxs-lookup"><span data-stu-id="ba204-112">Integration tests.</span></span> <span data-ttu-id="ba204-113">Garantem que as interações do componente funcionam como esperado em artefatos externos, como bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="ba204-113">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="ba204-114">Instruções assert podem testar a API do componente, a interface do usuário ou os efeitos colaterais de ações, como E/S de banco de dados, registros em log etc.</span><span class="sxs-lookup"><span data-stu-id="ba204-114">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

- <span data-ttu-id="ba204-115">Testes funcionais para cada microsserviço.</span><span class="sxs-lookup"><span data-stu-id="ba204-115">Functional tests for each microservice.</span></span> <span data-ttu-id="ba204-116">Eles garantem que o aplicativo funcione conforme o esperado da perspectiva do usuário.</span><span class="sxs-lookup"><span data-stu-id="ba204-116">These ensure that the application works as expected from the user's perspective.</span></span>

- <span data-ttu-id="ba204-117">Testes de serviço.</span><span class="sxs-lookup"><span data-stu-id="ba204-117">Service tests.</span></span> <span data-ttu-id="ba204-118">Garantem que os casos de uso do serviço de ponta a ponta sejam testados, incluindo testes de vários serviços ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ba204-118">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="ba204-119">Para esse tipo de teste, é necessário preparar o ambiente primeiro.</span><span class="sxs-lookup"><span data-stu-id="ba204-119">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="ba204-120">Nesse caso, isso significa iniciar os serviços (por exemplo, usando o Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="ba204-120">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="ba204-121">Implementar testes de unidade para APIs Web do ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ba204-121">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="ba204-122">O teste de unidade envolve o teste de uma parte de um aplicativo em isolamento de sua infraestrutura e suas dependências.</span><span class="sxs-lookup"><span data-stu-id="ba204-122">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="ba204-123">Ao executar a lógica do controlador de teste de unidade, somente o conteúdo de uma única ação ou método é testado, e não o comportamento de suas dependências ou da estrutura.</span><span class="sxs-lookup"><span data-stu-id="ba204-123">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="ba204-124">Os testes de unidade não detectam problemas na interação entre componentes, o que é a finalidade dos testes de integração.</span><span class="sxs-lookup"><span data-stu-id="ba204-124">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="ba204-125">Ao executar o teste de unidade nas ações do controlador, concentre-se apenas em seu comportamento.</span><span class="sxs-lookup"><span data-stu-id="ba204-125">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="ba204-126">Um teste de unidade de controlador evita itens como filtros, roteamento ou model binding (o mapeamento dos dados de solicitação a um ViewModel ou DTO).</span><span class="sxs-lookup"><span data-stu-id="ba204-126">A controller unit test avoids things like filters, routing, or model binding (the mapping of request data to a ViewModel or DTO).</span></span> <span data-ttu-id="ba204-127">Ao se concentrarem no teste de apenas um item, os testes de unidade geralmente são simples de serem gravados e rápidos de serem executados.</span><span class="sxs-lookup"><span data-stu-id="ba204-127">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="ba204-128">Um conjunto bem escrito de testes de unidade pode ser executado com frequência sem muita sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="ba204-128">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="ba204-129">Testes de unidade são implementados com base em estruturas de teste como xUnit.net, MSTest, Moq ou NUnit.</span><span class="sxs-lookup"><span data-stu-id="ba204-129">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="ba204-130">Para o aplicativo de exemplo eShopOnContainers, estamos usando o xUnit.</span><span class="sxs-lookup"><span data-stu-id="ba204-130">For the eShopOnContainers sample application, we are using xUnit.</span></span>

<span data-ttu-id="ba204-131">Ao gravar um teste de unidade de um controlador de API Web, você cria instâncias da classe do controlador usando diretamente a nova palavra-chave no C\#, para que o teste seja executado o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="ba204-131">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="ba204-132">O exemplo a seguir mostra como fazer isso usando o [xUnit](https://xunit.net/) como a estrutura de teste.</span><span class="sxs-lookup"><span data-stu-id="ba204-132">The following example shows how to do this when using [xUnit](https://xunit.net/) as the Test framework.</span></span>

```csharp
[Fact]
public async Task Get_order_detail_success()
{
    //Arrange
    var fakeOrderId = "12";
    var fakeOrder = GetFakeOrder();

    //...

    //Act
    var orderController = new OrderController(
        _orderServiceMock.Object,
        _basketServiceMock.Object,
        _identityParserMock.Object);

    orderController.ControllerContext.HttpContext = _contextMock.Object;
    var actionResult = await orderController.Detail(fakeOrderId);

    //Assert
    var viewResult = Assert.IsType<ViewResult>(actionResult);
    Assert.IsAssignableFrom<Order>(viewResult.ViewData.Model);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="ba204-133">Implementar testes funcionais e de integração em cada microsserviço</span><span class="sxs-lookup"><span data-stu-id="ba204-133">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="ba204-134">Conforme observado, testes funcionais e de integração têm finalidades e objetivos diferentes.</span><span class="sxs-lookup"><span data-stu-id="ba204-134">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="ba204-135">No entanto, a maneira de implementar ambos ao testar os controladores do ASP.NET Core é semelhante. Nesta seção, o foco é o teste de integração.</span><span class="sxs-lookup"><span data-stu-id="ba204-135">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="ba204-136">Testes de integração garantem que os componentes de um aplicativo funcionem corretamente quando montados.</span><span class="sxs-lookup"><span data-stu-id="ba204-136">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="ba204-137">O ASP.NET Core é compatível com testes de integração por meio de estruturas de teste de unidade e um host Web de testes interno que pode ser utilizado para lidar com solicitações sem sobrecarga de rede.</span><span class="sxs-lookup"><span data-stu-id="ba204-137">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="ba204-138">Ao contrário do teste de unidade, os testes de integração frequentemente envolvem questões relacionadas com a infraestrutura do aplicativo, como banco de dados, sistema de arquivos, recurso de rede ou solicitações e respostas da Web.</span><span class="sxs-lookup"><span data-stu-id="ba204-138">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="ba204-139">Testes de unidade usam objetos falsos ou fictícios em vez disso.</span><span class="sxs-lookup"><span data-stu-id="ba204-139">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="ba204-140">Porém, a finalidade dos testes de integração é confirmar que o sistema funciona como o esperado com esses sistemas. Então, nos testes de integração não se usam objetos falsos ou fictícios.</span><span class="sxs-lookup"><span data-stu-id="ba204-140">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="ba204-141">Em vez disso, você inclui a infraestrutura, como acesso ao banco de dados ou invocação de serviço de outros serviços.</span><span class="sxs-lookup"><span data-stu-id="ba204-141">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="ba204-142">Como os testes de integração exercitam segmentos de código maiores que os testes de unidade e contam com elementos de infraestrutura, eles tendem a ter ordens de magnitude mais lentas que os testes de unidade.</span><span class="sxs-lookup"><span data-stu-id="ba204-142">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="ba204-143">Portanto, é uma boa ideia limitar a quantidade de testes de integração gravados e executados.</span><span class="sxs-lookup"><span data-stu-id="ba204-143">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="ba204-144">O ASP.NET Core inclui um host Web de teste interno que pode ser usado para lidar com solicitações HTTP sem sobrecarga de rede, o que significa que você pode executar esses testes mais rápido do que ao usar um host Web real.</span><span class="sxs-lookup"><span data-stu-id="ba204-144">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster than when using a real web host.</span></span> <span data-ttu-id="ba204-145">O host Web de testes (TestServer) está disponível em um componente NuGet como Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="ba204-145">The test web host (TestServer) is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="ba204-146">Ele pode ser adicionado a projetos de teste de integração e usados para hospedar aplicativos do ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ba204-146">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="ba204-147">Conforme mostrado no código a seguir, ao criar testes de integração para controladores do ASP.NET Core, você cria instâncias para os controladores por meio do host de teste.</span><span class="sxs-lookup"><span data-stu-id="ba204-147">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="ba204-148">Isso é equivalente a uma solicitação HTTP, mas ele é executado mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="ba204-148">This is comparable to an HTTP request, but it runs faster.</span></span>

```csharp
public class PrimeWebDefaultRequestShould
{
    private readonly TestServer _server;
    private readonly HttpClient _client;

    public PrimeWebDefaultRequestShould()
    {
        // Arrange
        _server = new TestServer(new WebHostBuilder()
           .UseStartup<Startup>());
           _client = _server.CreateClient();
    }

    [Fact]
    public async Task ReturnHelloWorld()
    {
        // Act
        var response = await _client.GetAsync("/");
        response.EnsureSuccessStatusCode();
        var responseString = await response.Content.ReadAsStringAsync();
        // Assert
        Assert.Equal("Hello World!", responseString);
    }
}
```

#### <a name="additional-resources"></a><span data-ttu-id="ba204-149">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ba204-149">Additional resources</span></span>

- <span data-ttu-id="ba204-150">**Steve Smith. Testando controladores** (ASP.NET Core) </span><span class="sxs-lookup"><span data-stu-id="ba204-150">**Steve Smith. Testing controllers** (ASP.NET Core) </span></span>\
    [https://docs.microsoft.com/aspnet/core/mvc/controllers/testing](/aspnet/core/mvc/controllers/testing)

- <span data-ttu-id="ba204-151">**Steve Smith. Testes de integração** (ASP.NET Core) </span><span class="sxs-lookup"><span data-stu-id="ba204-151">**Steve Smith. Integration testing** (ASP.NET Core) </span></span>\
    [https://docs.microsoft.com/aspnet/core/test/integration-tests](/aspnet/core/test/integration-tests)

- <span data-ttu-id="ba204-152">**Teste de unidade no .NET Core usando o teste dotnet** </span><span class="sxs-lookup"><span data-stu-id="ba204-152">**Unit testing in .NET Core using dotnet test** </span></span>\
    [https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test](../../../core/testing/unit-testing-with-dotnet-test.md)

- <span data-ttu-id="ba204-153">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="ba204-153">**xUnit.net**.</span></span> <span data-ttu-id="ba204-154">Site oficial.</span><span class="sxs-lookup"><span data-stu-id="ba204-154">Official site.</span></span> \
    <https://xunit.net/>

- <span data-ttu-id="ba204-155">**Noções básicas do teste de unidade.**</span><span class="sxs-lookup"><span data-stu-id="ba204-155">**Unit Test Basics.**</span></span> \
    [https://docs.microsoft.com/visualstudio/test/unit-test-basics](/visualstudio/test/unit-test-basics)

- <span data-ttu-id="ba204-156">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="ba204-156">**Moq**.</span></span> <span data-ttu-id="ba204-157">Repositório do GitHub.</span><span class="sxs-lookup"><span data-stu-id="ba204-157">GitHub repo.</span></span> \
    <https://github.com/moq/moq>

- <span data-ttu-id="ba204-158">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="ba204-158">**NUnit**.</span></span> <span data-ttu-id="ba204-159">Site oficial.</span><span class="sxs-lookup"><span data-stu-id="ba204-159">Official site.</span></span> \
    <https://nunit.org/>

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="ba204-160">Implementar testes de serviço em um aplicativo com vários contêineres</span><span class="sxs-lookup"><span data-stu-id="ba204-160">Implementing service tests on a multi-container application</span></span>

<span data-ttu-id="ba204-161">Conforme mencionado anteriormente, ao testar aplicativos com vários contêineres, todos os microsserviços precisam ser executados no host do Docker ou no cluster do contêiner.</span><span class="sxs-lookup"><span data-stu-id="ba204-161">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="ba204-162">Testes de serviço de ponta a ponta que incluem várias operações que envolvem diversos microsserviços exigem a implantação e inicialização do aplicativo inteiro no host do Docker por meio da execução do Docker Compose (ou um mecanismo semelhante se você estiver usando um orquestrador).</span><span class="sxs-lookup"><span data-stu-id="ba204-162">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="ba204-163">Quando o aplicativo inteiro e todos os seus serviços estiverem em execução, você pode executar testes funcionais e de integração de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="ba204-163">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="ba204-164">Existem algumas abordagens que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="ba204-164">There are a few approaches you can use.</span></span> <span data-ttu-id="ba204-165">No arquivo docker-compose.yml usado para implantar o aplicativo, é possível expandir o ponto de entrada no nível da solução para usar o [dotnet test](../../../core/tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="ba204-165">In the docker-compose.yml file that you use to deploy the application at the solution level you can expand the entry point to use [dotnet test](../../../core/tools/dotnet-test.md).</span></span> <span data-ttu-id="ba204-166">Também é possível usar outro arquivo do Compose para executar testes na imagem de destino.</span><span class="sxs-lookup"><span data-stu-id="ba204-166">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="ba204-167">Ao utilizar outro arquivo do Compose para testes de integração que inclui microsserviços e bancos de dados em contêineres, você garante que dados relacionados sempre sejam redefinidos para seu estado original antes de executar os testes.</span><span class="sxs-lookup"><span data-stu-id="ba204-167">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="ba204-168">Se o Visual Studio estiver em execução, será possível aproveitar pontos de interrupção e exceções após o aplicativo do Compose entrar em funcionamento.</span><span class="sxs-lookup"><span data-stu-id="ba204-168">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="ba204-169">Outra opção é executar os testes de integração automaticamente no pipeline de CI no Azure DevOps Services ou em qualquer outro sistema CI/CD compatível com contêineres do Docker.</span><span class="sxs-lookup"><span data-stu-id="ba204-169">Or you can run the integration tests automatically in your CI pipeline in Azure DevOps Services or any other CI/CD system that supports Docker containers.</span></span>

## <a name="testing-in-eshoponcontainers"></a><span data-ttu-id="ba204-170">Testando em eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="ba204-170">Testing in eShopOnContainers</span></span>

<span data-ttu-id="ba204-171">Os testes do aplicativo (eShopOnContainers) de referência foram recentemente restruturados e agora há quatro categorias:</span><span class="sxs-lookup"><span data-stu-id="ba204-171">The reference application (eShopOnContainers) tests were recently restructured and now there are four categories:</span></span>

1. <span data-ttu-id="ba204-172">**Unidade** testa, os antigos testes de unidade regulares, contidos nos projetos **{MicroserviceName}.UnitTests**</span><span class="sxs-lookup"><span data-stu-id="ba204-172">**Unit** tests, just plain old regular unit tests, contained in the **{MicroserviceName}.UnitTests** projects</span></span>

2. <span data-ttu-id="ba204-173">**Testes funcionais/integração de microsserviço**, com casos de teste que envolvem a infraestrutura para cada microsserviço, mas isolado dos outros; estão contidos nos projetos **{MicroserviceName}.FunctionalTests**.</span><span class="sxs-lookup"><span data-stu-id="ba204-173">**Microservice functional/integration tests**, with test cases involving the infrastructure for each microservice but isolated from the others and are contained in the **{MicroserviceName}.FunctionalTests** projects.</span></span>

3. <span data-ttu-id="ba204-174">**Testes funcionais/de integração do aplicativo**, que se concentram na integração de microserviços, com casos de teste que exercem vários microserviços.</span><span class="sxs-lookup"><span data-stu-id="ba204-174">**Application functional/integration tests**, which focus on microservices integration, with test cases that exert several microservices.</span></span> <span data-ttu-id="ba204-175">Esses testes estão localizados no projeto **Application.FunctionalTests**.</span><span class="sxs-lookup"><span data-stu-id="ba204-175">These tests are located in project **Application.FunctionalTests**.</span></span>

<span data-ttu-id="ba204-176">Enquanto os testes de unidade e de integração são organizados em uma pasta de teste dentro do projeto de microserviço, os testes de carga e de aplicativo são gerenciados separadamente na pasta raiz, como mostra a Figura 6-25.</span><span class="sxs-lookup"><span data-stu-id="ba204-176">While unit and integration tests are organized in a test folder within the microservice project, application and load tests are managed separately under the root folder, as shown in Figure 6-25.</span></span>

![Captura de tela do VS apontando alguns dos projetos de teste na solução.](./media/test-aspnet-core-services-web-apps/eshoponcontainers-test-folder-structure.png)

<span data-ttu-id="ba204-178">**Figura 6-25**.</span><span class="sxs-lookup"><span data-stu-id="ba204-178">**Figure 6-25**.</span></span> <span data-ttu-id="ba204-179">Estrutura da pastas de teste em eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="ba204-179">Test folder structure in eShopOnContainers</span></span>

<span data-ttu-id="ba204-180">Testes funcionais/integração de aplicativos e microsserviços são executados no Visual Studio, usando o executor de testes regular, mas primeiro você precisa iniciar os serviços de infraestrutura necessários, por meio de um conjunto de arquivos docker-compose contidos na pasta de teste da solução:</span><span class="sxs-lookup"><span data-stu-id="ba204-180">Microservice and Application functional/integration tests are run from Visual Studio, using the regular tests runner, but first you need to start the required infrastructure services, by means of a set of docker-compose files contained in the solution test folder:</span></span>

<span data-ttu-id="ba204-181">**docker-compose-test.yml**</span><span class="sxs-lookup"><span data-stu-id="ba204-181">**docker-compose-test.yml**</span></span>

```yml
version: '3.4'

services:
  redis.data:
    image: redis:alpine
  rabbitmq:
    image: rabbitmq:3-management-alpine
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
  nosqldata:
    image: mongo
```

<span data-ttu-id="ba204-182">**docker-compose-test.override.yml**</span><span class="sxs-lookup"><span data-stu-id="ba204-182">**docker-compose-test.override.yml**</span></span>

```yml
version: '3.4'

services:
  redis.data:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"
  sqldata:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
```

<span data-ttu-id="ba204-183">Portanto, para executar os testes funcionais/integração, primeiro você deve executar esse comando na pasta de teste da solução:</span><span class="sxs-lookup"><span data-stu-id="ba204-183">So, to run the functional/integration tests you must first run this command, from the solution test folder:</span></span>

```console
docker-compose -f docker-compose-test.yml -f docker-compose-test.override.yml up
```

<span data-ttu-id="ba204-184">Como você pode ver, esses arquivos docker-compose só iniciam os microsserviços Redis, RabbitMQ, SQL Server e MongoDB.</span><span class="sxs-lookup"><span data-stu-id="ba204-184">As you can see, these docker-compose files only start the Redis, RabbitMQ, SQL Server and MongoDB microservices.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ba204-185">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ba204-185">Additional resources</span></span>

- <span data-ttu-id="ba204-186">**Teste de integração de & de unidade** no eShopOnContainers </span><span class="sxs-lookup"><span data-stu-id="ba204-186">**Unit & Integration testing** on the eShopOnContainers </span></span>\
    <https://github.com/dotnet-architecture/eShopOnContainers/wiki/Unit-and-integration-testing>

- <span data-ttu-id="ba204-187">**Teste de carga** no eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="ba204-187">**Load testing** on the eShopOnContainers \</span></span>
    <https://github.com/dotnet-architecture/eShopOnContainers/wiki/Load-testing>

> [!div class="step-by-step"]
> <span data-ttu-id="ba204-188">[Anterior](subscribe-events.md) 
>  [Avançar](background-tasks-with-ihostedservice.md)</span><span class="sxs-lookup"><span data-stu-id="ba204-188">[Previous](subscribe-events.md)
[Next](background-tasks-with-ihostedservice.md)</span></span>
