---
title: Usar injeção de dependência no .NET
description: Saiba como usar a injeção de dependência em seus aplicativos .NET.
author: IEvangelist
ms.author: dapine
ms.date: 11/13/2020
ms.topic: tutorial
no-loc:
- 'Transient'
- 'Scoped'
- 'Singleton'
- 'Example'
ms.openlocfilehash: b1e84685ad95372c4b2038e913199f7283135b71
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634514"
---
# <a name="tutorial-use-dependency-injection-in-net"></a><span data-ttu-id="d5b16-103">Tutorial: usar injeção de dependência no .NET</span><span class="sxs-lookup"><span data-stu-id="d5b16-103">Tutorial: Use dependency injection in .NET</span></span>

<span data-ttu-id="d5b16-104">Este tutorial mostra como usar [injeção de dependência (di) no .net](dependency-injection.md).</span><span class="sxs-lookup"><span data-stu-id="d5b16-104">This tutorial shows how to use [dependency injection (DI) in .NET](dependency-injection.md).</span></span> <span data-ttu-id="d5b16-105">Com *o Microsoft Extensions* , di é um cidadão de primeira classe onde os serviços são adicionados e configurados em um <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection> .</span><span class="sxs-lookup"><span data-stu-id="d5b16-105">With *Microsoft Extensions* , DI is a first-class citizen where services are added and configured in an <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="d5b16-106">A <xref:Microsoft.Extensions.Hosting.IHost> interface expõe a <xref:System.IServiceProvider> instância, que atua como um contêiner de todos os serviços registrados.</span><span class="sxs-lookup"><span data-stu-id="d5b16-106">The <xref:Microsoft.Extensions.Hosting.IHost> interface exposes the <xref:System.IServiceProvider> instance, which acts as a container of all the registered services.</span></span>

<span data-ttu-id="d5b16-107">Neste tutorial, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="d5b16-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="d5b16-108">Criar um aplicativo de console .NET que usa injeção de dependência</span><span class="sxs-lookup"><span data-stu-id="d5b16-108">Create a .NET console app that uses dependency injection</span></span>
> - <span data-ttu-id="d5b16-109">Criar e configurar um [host genérico](generic-host.md)</span><span class="sxs-lookup"><span data-stu-id="d5b16-109">Build and configure a [Generic Host](generic-host.md)</span></span>
> - <span data-ttu-id="d5b16-110">Escrever várias interfaces e implementações correspondentes</span><span class="sxs-lookup"><span data-stu-id="d5b16-110">Write several interfaces and corresponding implementations</span></span>
> - <span data-ttu-id="d5b16-111">Usar o tempo de vida do serviço e o escopo para DI</span><span class="sxs-lookup"><span data-stu-id="d5b16-111">Use service lifetime and scoping for DI</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d5b16-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d5b16-112">Prerequisites</span></span>

- <span data-ttu-id="d5b16-113">[SDK do .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="d5b16-113">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or later.</span></span>
- <span data-ttu-id="d5b16-114">Familiaridade com a criação de novos aplicativos .NET e a instalação de pacotes NuGet.</span><span class="sxs-lookup"><span data-stu-id="d5b16-114">Familiarity with creating new .NET applications and installing NuGet packages.</span></span>

## <a name="create-a-new-console-application"></a><span data-ttu-id="d5b16-115">Criar um novo aplicativo de console</span><span class="sxs-lookup"><span data-stu-id="d5b16-115">Create a new console application</span></span>

<span data-ttu-id="d5b16-116">Usando o comando [dotnet New](../tools/dotnet-new.md) ou um assistente de novo projeto do IDE, crie um novo aplicativo de console .NET chamado **ConsoleDI. Example**.</span><span class="sxs-lookup"><span data-stu-id="d5b16-116">Using either the [dotnet new](../tools/dotnet-new.md) command or an IDE new project wizard, create a new .NET console application named **ConsoleDI.Example**.</span></span> <span data-ttu-id="d5b16-117">Adicione o pacote NuGet [Microsoft. Extensions. Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) ao projeto.</span><span class="sxs-lookup"><span data-stu-id="d5b16-117">Add the [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet package to the project.</span></span>

## <a name="add-interfaces"></a><span data-ttu-id="d5b16-118">Adicionar interfaces</span><span class="sxs-lookup"><span data-stu-id="d5b16-118">Add interfaces</span></span>

<span data-ttu-id="d5b16-119">Adicione as seguintes interfaces ao diretório raiz do projeto:</span><span class="sxs-lookup"><span data-stu-id="d5b16-119">Add the following interfaces to the project root directory:</span></span>

<span data-ttu-id="d5b16-120">*IOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="d5b16-120">*IOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

<span data-ttu-id="d5b16-121">A `IOperation` interface define uma única `OperationId` propriedade.</span><span class="sxs-lookup"><span data-stu-id="d5b16-121">The `IOperation` interface defines a single `OperationId` property.</span></span>

<span data-ttu-id="d5b16-122">*Eu Transient Operation.cs*</span><span class="sxs-lookup"><span data-stu-id="d5b16-122">*ITransientOperation.cs*</span></span>

<span data-ttu-id="d5b16-123">::: linguagem de código = "CSharp" origem = "trechos/configuração/console-di/I Transient Operation.cs":::</span><span class="sxs-lookup"><span data-stu-id="d5b16-123">:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::</span></span>

<span data-ttu-id="d5b16-124">*Eu Scoped Operation.cs*</span><span class="sxs-lookup"><span data-stu-id="d5b16-124">*IScopedOperation.cs*</span></span>

<span data-ttu-id="d5b16-125">::: linguagem de código = "CSharp" origem = "trechos/configuração/console-di/I Scoped Operation.cs":::</span><span class="sxs-lookup"><span data-stu-id="d5b16-125">:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::</span></span>

<span data-ttu-id="d5b16-126">*Eu Singleton Operation.cs*</span><span class="sxs-lookup"><span data-stu-id="d5b16-126">*ISingletonOperation.cs*</span></span>

<span data-ttu-id="d5b16-127">::: linguagem de código = "CSharp" origem = "trechos/configuração/console-di/I Singleton Operation.cs":::</span><span class="sxs-lookup"><span data-stu-id="d5b16-127">:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::</span></span>

<span data-ttu-id="d5b16-128">Todas as subinterfaces de `IOperation` nome do seu tempo de vida de serviço pretendido.</span><span class="sxs-lookup"><span data-stu-id="d5b16-128">All of the subinterfaces of `IOperation` name their intended service lifetime.</span></span> <span data-ttu-id="d5b16-129">Por exemplo, " Transient " ou " Singleton ".</span><span class="sxs-lookup"><span data-stu-id="d5b16-129">For example, "Transient" or "Singleton".</span></span>

## <a name="add-default-implementation"></a><span data-ttu-id="d5b16-130">Adicionar implementação padrão</span><span class="sxs-lookup"><span data-stu-id="d5b16-130">Add default implementation</span></span>

<span data-ttu-id="d5b16-131">Adicione a seguinte implementação padrão para as várias operações:</span><span class="sxs-lookup"><span data-stu-id="d5b16-131">Add the following default implementation for the various operations:</span></span>

<span data-ttu-id="d5b16-132">*DefaultOperation.cs*</span><span class="sxs-lookup"><span data-stu-id="d5b16-132">*DefaultOperation.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

<span data-ttu-id="d5b16-133">O `DefaultOperation` implementa todas as interfaces do marcador nomeado e inicializa a `OperationId` propriedade para os últimos quatro caracteres de um novo GUID (identificador global exclusivo).</span><span class="sxs-lookup"><span data-stu-id="d5b16-133">The `DefaultOperation` implements all of the named marker interfaces and initializes the `OperationId` property to the last four characters of a new globally unique identifier (GUID).</span></span>

## <a name="add-service-that-requires-di"></a><span data-ttu-id="d5b16-134">Adicionar serviço que requer DI</span><span class="sxs-lookup"><span data-stu-id="d5b16-134">Add service that requires DI</span></span>

<span data-ttu-id="d5b16-135">Adicione o seguinte objeto de agente de operação, que atua como um serviço para o aplicativo de console:</span><span class="sxs-lookup"><span data-stu-id="d5b16-135">Add the following operation logger object, which acts as a service to the console app:</span></span>

<span data-ttu-id="d5b16-136">*OperationLogger.cs*</span><span class="sxs-lookup"><span data-stu-id="d5b16-136">*OperationLogger.cs*</span></span>

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

<span data-ttu-id="d5b16-137">O `OperationLogger` define um construtor que requer cada uma das interfaces de marcador mencionadas anteriormente, ou seja,, `ITransientOperation` `IScopedOperation` e `ISingletonOperation` .</span><span class="sxs-lookup"><span data-stu-id="d5b16-137">The `OperationLogger` defines a constructor that requires each of the aforementioned marker interfaces, that is; `ITransientOperation`, `IScopedOperation`, and `ISingletonOperation`.</span></span> <span data-ttu-id="d5b16-138">O objeto expõe um único método que permite ao consumidor registrar as operações com um determinado `scope` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d5b16-138">The object exposes a single method that allows the consumer to log the operations with a given `scope` parameter.</span></span> <span data-ttu-id="d5b16-139">Quando invocado, o `LogOperations` método registra o identificador exclusivo de cada operação com a cadeia de caracteres e a mensagem do escopo.</span><span class="sxs-lookup"><span data-stu-id="d5b16-139">When invoked, the `LogOperations` method logs each operation's unique identifier with the scope string and message.</span></span>

## <a name="register-services-for-di"></a><span data-ttu-id="d5b16-140">Registrar serviços para DI</span><span class="sxs-lookup"><span data-stu-id="d5b16-140">Register services for DI</span></span>

<span data-ttu-id="d5b16-141">Atualize *Program.cs* com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="d5b16-141">Update *Program.cs* with the following code:</span></span>

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

> <span data-ttu-id="d5b16-142">Cada `services.Add{SERVICE_NAME}` método de extensão adiciona e potencialmente configura os serviços do.</span><span class="sxs-lookup"><span data-stu-id="d5b16-142">Each `services.Add{SERVICE_NAME}` extension method adds, and potentially configures, services.</span></span> <span data-ttu-id="d5b16-143">Recomendamos que os aplicativos sigam essa convenção.</span><span class="sxs-lookup"><span data-stu-id="d5b16-143">We recommended that apps follow this convention.</span></span> <span data-ttu-id="d5b16-144">Coloque os métodos de extensão no namespace <xref:Microsoft.Extensions.DependencyInjection?displayProperty=fullName> para encapsular grupos de registros de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5b16-144">Place extension methods in the <xref:Microsoft.Extensions.DependencyInjection?displayProperty=fullName> namespace to encapsulate groups of service registrations.</span></span> <span data-ttu-id="d5b16-145">Incluir a porção `Microsoft.Extensions.DependencyInjection` de namespace para métodos de extensão de di também:</span><span class="sxs-lookup"><span data-stu-id="d5b16-145">Including the namespace portion `Microsoft.Extensions.DependencyInjection` for DI extension methods also:</span></span>
>
> - <span data-ttu-id="d5b16-146">Permite que eles sejam exibidos no [IntelliSense](/visualstudio/ide/using-intellisense) sem adicionar `using` blocos adicionais.</span><span class="sxs-lookup"><span data-stu-id="d5b16-146">Allows them to be displayed in [IntelliSense](/visualstudio/ide/using-intellisense) without adding additional `using` blocks.</span></span>
> - <span data-ttu-id="d5b16-147">Impede instruções excessivas `using` nas `Program` `Startup` classes ou em que esses métodos de extensão são chamados normalmente.</span><span class="sxs-lookup"><span data-stu-id="d5b16-147">Prevents excessive `using` statements in the `Program` or `Startup` classes where these extension methods are typically called.</span></span>

<span data-ttu-id="d5b16-148">O aplicativo:</span><span class="sxs-lookup"><span data-stu-id="d5b16-148">The app:</span></span>

- <span data-ttu-id="d5b16-149">Cria uma <xref:Microsoft.Extensions.Hosting.IHostBuilder> instância com as [configurações padrão do fichário](generic-host.md#default-builder-settings).</span><span class="sxs-lookup"><span data-stu-id="d5b16-149">Creates an <xref:Microsoft.Extensions.Hosting.IHostBuilder> instance with the [default binder settings](generic-host.md#default-builder-settings).</span></span>
- <span data-ttu-id="d5b16-150">Configura os serviços e os adiciona com o tempo de vida do serviço correspondente.</span><span class="sxs-lookup"><span data-stu-id="d5b16-150">Configures services and adds them with their corresponding service lifetime.</span></span>
- <span data-ttu-id="d5b16-151">Chama <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> e atribui uma instância do <xref:Microsoft.Extensions.Hosting.IHost> .</span><span class="sxs-lookup"><span data-stu-id="d5b16-151">Calls <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> and assigns an instance of <xref:Microsoft.Extensions.Hosting.IHost>.</span></span>
- <span data-ttu-id="d5b16-152">Chamadas `ExemplifyScoping` , passando no <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d5b16-152">Calls `ExemplifyScoping`, passing in the <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>.</span></span>

## <a name="conclusion"></a><span data-ttu-id="d5b16-153">Conclusão</span><span class="sxs-lookup"><span data-stu-id="d5b16-153">Conclusion</span></span>

<span data-ttu-id="d5b16-154">O aplicativo exibe uma saída semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="d5b16-154">The app displays output similar to the following example:</span></span>

```console
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ 80f4...Always different        ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ f3c0...Always different        ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]

Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ f9af...Always different        ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ fa65...Always different        ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
```

<span data-ttu-id="d5b16-155">Na saída do aplicativo, você pode ver que:</span><span class="sxs-lookup"><span data-stu-id="d5b16-155">From the app output, you can see that:</span></span>

- <span data-ttu-id="d5b16-156">Transient as operações são sempre diferentes, uma nova instância é criada com cada recuperação do serviço.</span><span class="sxs-lookup"><span data-stu-id="d5b16-156">Transient operations are always different, a new instance is created with every retrieval of the service.</span></span>
- <span data-ttu-id="d5b16-157">Scoped as operações são alteradas somente com um novo escopo, mas são a mesma instância dentro de um escopo.</span><span class="sxs-lookup"><span data-stu-id="d5b16-157">Scoped operations change only with a new scope, but are the same instance within a scope.</span></span>
- <span data-ttu-id="d5b16-158">Singleton as operações são sempre as mesmas, uma nova instância é criada apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="d5b16-158">Singleton operations are always the same, a new instance is only created once.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5b16-159">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d5b16-159">See also</span></span>

* [<span data-ttu-id="d5b16-160">Diretrizes de injeção de dependência</span><span class="sxs-lookup"><span data-stu-id="d5b16-160">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
* [<span data-ttu-id="d5b16-161">Injeção de dependência no ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d5b16-161">Dependency injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)
