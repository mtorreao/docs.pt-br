---
title: 'Tutorial: criar uma ferramenta .NET'
description: Saiba como criar uma ferramenta .NET. Uma ferramenta é um aplicativo de console que é instalado usando a CLI do .NET.
ms.topic: tutorial
ms.date: 02/12/2020
ms.openlocfilehash: 8f2dd15982aff9fe2d9db9ce2cff8ac1b22e440e
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512626"
---
# <a name="tutorial-create-a-net-tool-using-the-net-cli"></a><span data-ttu-id="0f61d-104">Tutorial: criar uma ferramenta .NET usando a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="0f61d-104">Tutorial: Create a .NET tool using the .NET CLI</span></span>

<span data-ttu-id="0f61d-105">**Este artigo aplica-se a:** ✔️ SDK do .net Core 2,1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="0f61d-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="0f61d-106">Este tutorial ensina como criar e empacotar uma ferramenta .NET.</span><span class="sxs-lookup"><span data-stu-id="0f61d-106">This tutorial teaches you how to create and package a .NET tool.</span></span> <span data-ttu-id="0f61d-107">A CLI do .NET permite criar um aplicativo de console como uma ferramenta, que outras pessoas podem instalar e executar.</span><span class="sxs-lookup"><span data-stu-id="0f61d-107">The .NET CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="0f61d-108">As ferramentas .NET são pacotes NuGet que são instalados a partir da CLI do .NET.</span><span class="sxs-lookup"><span data-stu-id="0f61d-108">.NET tools are NuGet packages that are installed from the .NET CLI.</span></span> <span data-ttu-id="0f61d-109">Para obter mais informações sobre ferramentas, consulte [visão geral das ferramentas .net](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0f61d-109">For more information about tools, see [.NET tools overview](global-tools.md).</span></span>

<span data-ttu-id="0f61d-110">A ferramenta que você criará é um aplicativo de console que recebe uma mensagem como entrada e exibe a mensagem junto com linhas de texto que criam a imagem de um robô.</span><span class="sxs-lookup"><span data-stu-id="0f61d-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="0f61d-111">Este é o primeiro de uma série de três tutoriais.</span><span class="sxs-lookup"><span data-stu-id="0f61d-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="0f61d-112">Neste tutorial, você criará e empacotará uma ferramenta.</span><span class="sxs-lookup"><span data-stu-id="0f61d-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="0f61d-113">Nos próximos dois tutoriais, você [usará a ferramenta como uma ferramenta global](global-tools-how-to-use.md) e [usará a ferramenta como uma ferramenta local](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="0f61d-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span> <span data-ttu-id="0f61d-114">Os procedimentos para criar uma ferramenta são os mesmos se você usá-la como uma ferramenta global ou como uma ferramenta local.</span><span class="sxs-lookup"><span data-stu-id="0f61d-114">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f61d-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0f61d-115">Prerequisites</span></span>

- <span data-ttu-id="0f61d-116">[SDK do .net 5,0](https://dotnet.microsoft.com/download) ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="0f61d-116">[.NET SDK 5.0](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="0f61d-117">Este tutorial usa o SDK do .NET 5,0, mas as ferramentas globais estão disponíveis a partir do SDK do .NET Core 2,1.</span><span class="sxs-lookup"><span data-stu-id="0f61d-117">This tutorial uses .NET SDK 5.0, but global tools are available starting in .NET Core SDK 2.1.</span></span> <span data-ttu-id="0f61d-118">As ferramentas locais estão disponíveis a partir do SDK do .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="0f61d-118">Local tools are available starting in .NET Core SDK 3.0.</span></span>
  
- <span data-ttu-id="0f61d-119">Um editor de texto ou editor de código de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="0f61d-119">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="0f61d-120">Criar um projeto</span><span class="sxs-lookup"><span data-stu-id="0f61d-120">Create a project</span></span>

1. <span data-ttu-id="0f61d-121">Abra um prompt de comando e crie uma pasta chamada *Repository*.</span><span class="sxs-lookup"><span data-stu-id="0f61d-121">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="0f61d-122">Navegue até a pasta *repositório* e insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0f61d-122">Navigate to the *repository* folder and enter the following command:</span></span>

   ```dotnetcli
   dotnet new console -n microsoft.botsay
   ```

   <span data-ttu-id="0f61d-123">O comando cria uma nova pasta chamada *Microsoft. botsay* na pasta *Repository* .</span><span class="sxs-lookup"><span data-stu-id="0f61d-123">The command creates a new folder named *microsoft.botsay* under the *repository* folder.</span></span>

1. <span data-ttu-id="0f61d-124">Navegue até a pasta *Microsoft. botsay* .</span><span class="sxs-lookup"><span data-stu-id="0f61d-124">Navigate to the *microsoft.botsay* folder.</span></span>

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a><span data-ttu-id="0f61d-125">Adicionar o código</span><span class="sxs-lookup"><span data-stu-id="0f61d-125">Add the code</span></span>

1. <span data-ttu-id="0f61d-126">Abra o `Program.cs` arquivo com seu editor de código.</span><span class="sxs-lookup"><span data-stu-id="0f61d-126">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="0f61d-127">Adicione a seguinte `using` diretiva à parte superior do arquivo:</span><span class="sxs-lookup"><span data-stu-id="0f61d-127">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="0f61d-128">Substitua o `Main` método pelo código a seguir para processar os argumentos de linha de comando para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f61d-128">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   <span data-ttu-id="0f61d-129">Se nenhum argumento for passado, será exibida uma mensagem de ajuda curta.</span><span class="sxs-lookup"><span data-stu-id="0f61d-129">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="0f61d-130">Caso contrário, todos os argumentos são concatenados em uma única cadeia de caracteres e impressos chamando o `ShowBot` método que você cria na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="0f61d-130">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="0f61d-131">Adicione um novo método chamado `ShowBot` que usa um parâmetro de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f61d-131">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="0f61d-132">O método imprime a mensagem e uma imagem de um robô usando linhas de texto.</span><span class="sxs-lookup"><span data-stu-id="0f61d-132">The method prints out the message and an image of a robot using lines of text.</span></span>

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. <span data-ttu-id="0f61d-133">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="0f61d-133">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="0f61d-134">Testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="0f61d-134">Test the application</span></span>

<span data-ttu-id="0f61d-135">Execute o projeto e veja a saída.</span><span class="sxs-lookup"><span data-stu-id="0f61d-135">Run the project and see the output.</span></span> <span data-ttu-id="0f61d-136">Experimente essas variações na linha de comando para ver os resultados diferentes:</span><span class="sxs-lookup"><span data-stu-id="0f61d-136">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="0f61d-137">Todos os argumentos após o delimitador `--` são passados para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f61d-137">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="0f61d-138">Empacotar a ferramenta</span><span class="sxs-lookup"><span data-stu-id="0f61d-138">Package the tool</span></span>

<span data-ttu-id="0f61d-139">Antes de poder empacotar e distribuir o aplicativo como uma ferramenta, você precisa modificar o arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="0f61d-139">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span>

1. <span data-ttu-id="0f61d-140">Abra o arquivo *Microsoft. botsay. csproj* e adicione três novos nós XML ao final do `<PropertyGroup>` nó:</span><span class="sxs-lookup"><span data-stu-id="0f61d-140">Open the *microsoft.botsay.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="0f61d-141">`<ToolCommandName>` é um elemento opcional que especifica o comando que invocará a ferramenta após sua instalação.</span><span class="sxs-lookup"><span data-stu-id="0f61d-141">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="0f61d-142">Se esse elemento não for fornecido, o nome do comando para a ferramenta será o nome do arquivo de projeto sem a extensão *. csproj* .</span><span class="sxs-lookup"><span data-stu-id="0f61d-142">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="0f61d-143">`<PackageOutputPath>` é um elemento opcional que determina onde o pacote NuGet será produzido.</span><span class="sxs-lookup"><span data-stu-id="0f61d-143">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="0f61d-144">O pacote NuGet é o que a CLI do .NET usa para instalar sua ferramenta.</span><span class="sxs-lookup"><span data-stu-id="0f61d-144">The NuGet package is what the .NET CLI uses to install your tool.</span></span>

   <span data-ttu-id="0f61d-145">O arquivo de projeto agora é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="0f61d-145">The project file now looks like the following example:</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">
  
     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>net5.0</TargetFramework>
  
       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>
  
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="0f61d-146">Crie um pacote NuGet executando o comando [dotnet Pack](dotnet-pack.md) :</span><span class="sxs-lookup"><span data-stu-id="0f61d-146">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="0f61d-147">O arquivo *Microsoft. botsay. 1.0.0. nupkg* é criado na pasta identificada pelo `<PackageOutputPath>` valor do arquivo *Microsoft. botsay. csproj* , que neste exemplo é a pasta *./nupkg* .</span><span class="sxs-lookup"><span data-stu-id="0f61d-147">The *microsoft.botsay.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *microsoft.botsay.csproj* file, which in this example is the *./nupkg* folder.</span></span>
  
   <span data-ttu-id="0f61d-148">Quando você quiser liberar uma ferramenta publicamente, poderá carregá-la no `https://www.nuget.org` .</span><span class="sxs-lookup"><span data-stu-id="0f61d-148">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="0f61d-149">Depois que a ferramenta estiver disponível no NuGet, os desenvolvedores poderão instalar a ferramenta usando o comando [dotnet ferramenta de instalação](dotnet-tool-install.md) .</span><span class="sxs-lookup"><span data-stu-id="0f61d-149">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="0f61d-150">Para este tutorial, você instala o pacote diretamente da pasta *nupkg* local, portanto, não é necessário carregar o pacote no NuGet.</span><span class="sxs-lookup"><span data-stu-id="0f61d-150">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="0f61d-151">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="0f61d-151">Troubleshoot</span></span>

<span data-ttu-id="0f61d-152">Se você receber uma mensagem de erro ao seguir o tutorial, consulte [solucionar problemas de uso da ferramenta .net](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0f61d-152">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f61d-153">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="0f61d-153">Next steps</span></span>

<span data-ttu-id="0f61d-154">Neste tutorial, você criou um aplicativo de console e o empacotava como uma ferramenta.</span><span class="sxs-lookup"><span data-stu-id="0f61d-154">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="0f61d-155">Para saber como usar a ferramenta como uma ferramenta global, avance para o próximo tutorial.</span><span class="sxs-lookup"><span data-stu-id="0f61d-155">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0f61d-156">Instalar e usar uma ferramenta global</span><span class="sxs-lookup"><span data-stu-id="0f61d-156">Install and use a global tool</span></span>](global-tools-how-to-use.md)

<span data-ttu-id="0f61d-157">Se preferir, você pode ignorar o tutorial de ferramentas globais e ir diretamente para o tutorial de ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="0f61d-157">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0f61d-158">Instalar e usar uma ferramenta local</span><span class="sxs-lookup"><span data-stu-id="0f61d-158">Install and use a local tool</span></span>](local-tools-how-to-use.md)
