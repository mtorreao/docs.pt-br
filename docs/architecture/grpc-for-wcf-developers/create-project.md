---
title: Criar um novo projeto ASP.NET Core gRPC-gRPC para desenvolvedores do WCF
description: Saiba como criar um projeto gRPC usando o Visual Studio ou a linha de comando.
ms.date: 01/06/2021
ms.openlocfilehash: c9d66a773f0633c2ae93c42ce3ce53084032cd17
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970252"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="e7ffd-103">Criar um projeto ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="e7ffd-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="e7ffd-104">O SDK do .NET vem com uma poderosa ferramenta CLI, `dotnet` , que permite criar e gerenciar projetos e soluções na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-104">The .NET SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="e7ffd-105">O SDK está intimamente integrado ao Visual Studio, de modo que tudo também está disponível por meio da interface gráfica do usuário familiar.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="e7ffd-106">Este capítulo mostra as duas maneiras de criar um novo projeto ASP.NET Core gRPC.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="e7ffd-107">Criar o projeto usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7ffd-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7ffd-108">Para desenvolver qualquer aplicativo ASP.NET Core 5,0, você precisa do Visual Studio 2019 versão 16,8 ou posterior, com a ASP.NET e a carga de trabalho de **desenvolvimento Web** instaladas.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-108">To develop any ASP.NET Core 5.0 app, you need Visual Studio 2019 version 16.8 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="e7ffd-109">Crie uma solução vazia chamada **Traders** a partir do modelo de *solução em branco* .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="e7ffd-110">Adicione uma pasta de solução chamada `src` .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="e7ffd-111">Em seguida, clique com o botão direito do mouse na pasta e escolha **Adicionar**  >  **novo projeto**.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="e7ffd-112">Digite `grpc` na caixa de pesquisa de modelo e você deverá ver um modelo de projeto chamado `gRPC Service` .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![Captura de tela da caixa de diálogo Adicionar um novo projeto](media/create-project/new-grpc-project.png)

<span data-ttu-id="e7ffd-114">Selecione **Avançar** para continuar na caixa de diálogo **Configurar o novo projeto** .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="e7ffd-115">Nomeie o projeto `TraderSys.Portfolios` e adicione um `src` subdiretório ao **local**.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-115">Name the project `TraderSys.Portfolios` and add an `src` subdirectory to the **Location**.</span></span>

![Captura de tela da caixa de diálogo Configurar seu novo projeto](media/create-project/configure-project.png)

<span data-ttu-id="e7ffd-117">Selecione **Avançar** para continuar na caixa de diálogo **criar um novo serviço gRPC** .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![Captura de tela da caixa de diálogo criar um novo serviço gRPC](media/create-project/create-new-grpc-service-v2.png)

<span data-ttu-id="e7ffd-119">No momento, você tem opções limitadas para a criação do serviço.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="e7ffd-120">O Docker será introduzido posteriormente, por isso, por enquanto, deixe essa opção desmarcada.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="e7ffd-121">Basta selecionar **criar**.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-121">Just select **Create**.</span></span> <span data-ttu-id="e7ffd-122">Seu primeiro projeto ASP.NET Core gRPC 5,0 é gerado e adicionado à solução.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-122">Your first ASP.NET Core 5.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="e7ffd-123">Se você não quiser saber sobre como trabalhar com o `dotnet CLI` , pule para a seção [limpar o exemplo de código](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-cli"></a><span data-ttu-id="e7ffd-124">Criar o projeto usando a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="e7ffd-124">Create the project by using the .NET CLI</span></span>

<span data-ttu-id="e7ffd-125">Esta seção aborda a criação de soluções e projetos da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="e7ffd-126">Crie a solução, conforme mostrado no comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="e7ffd-127">O `-o` sinalizador (ou `--output` ) especifica o diretório de saída, que é criado no diretório atual, caso ele ainda não exista.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="e7ffd-128">A solução tem o mesmo nome que o diretório: `TraderSys.sln` .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="e7ffd-129">Você pode fornecer um nome diferente usando o `-n` sinalizador (ou `--name` ).</span><span class="sxs-lookup"><span data-stu-id="e7ffd-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="e7ffd-130">ASP.NET Core 5,0 vem com um modelo de CLI para serviços gRPCs.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-130">ASP.NET Core 5.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="e7ffd-131">Crie o novo projeto usando esse modelo, colocando-o em um `src` subdiretório como é convencional para projetos de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="e7ffd-132">O projeto é nomeado após o diretório ( `TraderSys.Portfolios.csproj` ), a menos que você especifique um nome diferente com o `-n` sinalizador.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="e7ffd-133">Por fim, adicione o projeto à solução usando o `dotnet sln` comando:</span><span class="sxs-lookup"><span data-stu-id="e7ffd-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="e7ffd-134">Como o diretório específico contém apenas um único `.csproj` arquivo, você pode especificar apenas o diretório, para salvar a digitação.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="e7ffd-135">Agora você pode abrir essa solução no Visual Studio 2019, Visual Studio Code ou em qualquer editor que preferir.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="e7ffd-136">Limpar o código de exemplo</span><span class="sxs-lookup"><span data-stu-id="e7ffd-136">Clean up the example code</span></span>

<span data-ttu-id="e7ffd-137">Agora você criou um serviço de exemplo usando o modelo gRPC, que foi revisado anteriormente no livro.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="e7ffd-138">Esse código não é útil em nosso contexto de comércio de ações, portanto, vamos editar as coisas para nosso primeiro projeto.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-138">This code isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="e7ffd-139">Renomear e editar o arquivo proto</span><span class="sxs-lookup"><span data-stu-id="e7ffd-139">Rename and edit the proto file</span></span>

<span data-ttu-id="e7ffd-140">Vá em frente e renomeie o `Protos/greet.proto` arquivo para `Protos/portfolios.proto` e abra-o em seu editor.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="e7ffd-141">Exclua tudo após a `package` linha.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="e7ffd-142">Em seguida, altere os `option csharp_namespace` nomes, e `package` `service` e remova o `SayHello` serviço padrão.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="e7ffd-143">O código agora é semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7ffd-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="e7ffd-144">O modelo não adiciona a `Protos` parte de namespace por padrão, mas adicioná-la torna mais fácil manter classes gRPC e suas próprias classes claramente separadas em seu código.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="e7ffd-145">Se você renomear o `greet.proto` arquivo em um ambiente de desenvolvimento integrado (IDE) como o Visual Studio, uma referência a esse arquivo será atualizada automaticamente no `.csproj` arquivo.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="e7ffd-146">Mas, em algum outro editor, como Visual Studio Code, essa referência não é atualizada automaticamente, portanto, você precisa editar o arquivo de projeto manualmente.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="e7ffd-147">Nos destinos de compilação gRPC, há um `Protobuf` elemento item que permite especificar quais `.proto` arquivos devem ser compilados e qual forma de geração de código é necessária (ou seja, "Server" ou "Client").</span><span class="sxs-lookup"><span data-stu-id="e7ffd-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="e7ffd-148">Renomear a `GreeterService` classe</span><span class="sxs-lookup"><span data-stu-id="e7ffd-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="e7ffd-149">A `GreeterService` classe está na `Services` pasta e herda de `Greeter.GreeterBase` .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="e7ffd-150">Renomeie- `PortfolioService` o para e altere a classe base para `Portfolios.PortfoliosBase` .</span><span class="sxs-lookup"><span data-stu-id="e7ffd-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="e7ffd-151">Exclua os `override` métodos.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="e7ffd-152">Houve uma referência à `GreeterService` classe no `Configure` método na `Startup` classe.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="e7ffd-153">Se você usou a refatoração para renomear a classe, essa referência deverá ter sido atualizada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="e7ffd-154">No entanto, se você não tiver, precisará editá-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-154">However, if you didn't, you need to edit it manually.</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="e7ffd-155">Na próxima seção, adicionaremos funcionalidade a esse novo serviço.</span><span class="sxs-lookup"><span data-stu-id="e7ffd-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e7ffd-156">[Anterior](migrate-wcf-to-grpc.md) 
> [Avançar](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="e7ffd-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
