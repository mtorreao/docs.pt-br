---
title: CLI do .NET
titleSuffix: ''
description: Uma visão geral da CLI do .NET e seus recursos.
ms.topic: overview
ms.date: 02/13/2020
ms.openlocfilehash: 6a12e2d16afe36092c10e14a7465fa3bdbb23f32
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633850"
---
# <a name="net-cli-overview"></a><span data-ttu-id="bb39c-103">Visão geral da CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="bb39c-103">.NET CLI overview</span></span>

<span data-ttu-id="bb39c-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 2,1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="bb39c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="bb39c-105">A CLI (interface de linha de comando) do .NET é uma ferramentas de plataforma cruzada para o desenvolvimento, a criação, a execução e a publicação de aplicativos .NET.</span><span class="sxs-lookup"><span data-stu-id="bb39c-105">The .NET command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET applications.</span></span>

<span data-ttu-id="bb39c-106">A CLI do .NET está incluída no [SDK do .net](../sdk.md).</span><span class="sxs-lookup"><span data-stu-id="bb39c-106">The .NET CLI is included with the [.NET SDK](../sdk.md).</span></span> <span data-ttu-id="bb39c-107">Para saber como instalar o SDK do .NET, consulte [instalar o .NET Core](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="bb39c-107">To learn how to install the .NET SDK, see [Install .NET Core](../install/windows.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="bb39c-108">Comandos de CLI</span><span class="sxs-lookup"><span data-stu-id="bb39c-108">CLI commands</span></span>

<span data-ttu-id="bb39c-109">Os comandos a seguir são instalados por padrão:</span><span class="sxs-lookup"><span data-stu-id="bb39c-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="bb39c-110">Comandos básicos</span><span class="sxs-lookup"><span data-stu-id="bb39c-110">Basic commands</span></span>

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="bb39c-111">Comandos de modificação de projeto</span><span class="sxs-lookup"><span data-stu-id="bb39c-111">Project modification commands</span></span>

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="bb39c-112">Comandos avançados</span><span class="sxs-lookup"><span data-stu-id="bb39c-112">Advanced commands</span></span>

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="bb39c-113">Comandos de gerenciamento de ferramentas</span><span class="sxs-lookup"><span data-stu-id="bb39c-113">Tool management commands</span></span>

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- <span data-ttu-id="bb39c-114">[`tool restore`](global-tools.md#install-a-local-tool) Disponível desde SDK do .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="bb39c-114">[`tool restore`](global-tools.md#install-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- <span data-ttu-id="bb39c-115">[`tool run`](global-tools.md#invoke-a-local-tool) Disponível desde SDK do .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="bb39c-115">[`tool run`](global-tools.md#invoke-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- [`tool uninstall`](dotnet-tool-uninstall.md)

<span data-ttu-id="bb39c-116">Ferramentas são aplicativos de console que são instalados a partir de pacotes NuGet e são invocados no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="bb39c-116">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="bb39c-117">Você pode escrever ferramentas por conta própria ou instalar ferramentas escritas por terceiros.</span><span class="sxs-lookup"><span data-stu-id="bb39c-117">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="bb39c-118">As ferramentas também são conhecidas como ferramentas globais, ferramentas de caminho de ferramenta e ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="bb39c-118">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="bb39c-119">Para obter mais informações, consulte [visão geral das ferramentas .net](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bb39c-119">For more information, see [.NET tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="bb39c-120">Estrutura de comando</span><span class="sxs-lookup"><span data-stu-id="bb39c-120">Command structure</span></span>

<span data-ttu-id="bb39c-121">A estrutura de comando CLI consiste no [driver ("dotnet")](#driver), [do comando](#command) e possivelmente de [opções](#options) e [argumentos](#arguments) de comando.</span><span class="sxs-lookup"><span data-stu-id="bb39c-121">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="bb39c-122">É possível ver esse padrão na maioria das operações de CLI, como ao criar um novo aplicativo de console e executá-lo a partir da linha de comando, como mostram os comandos a seguir quando executados a partir de um diretório chamado *my_app* :</span><span class="sxs-lookup"><span data-stu-id="bb39c-122">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app* :</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="bb39c-123">Driver</span><span class="sxs-lookup"><span data-stu-id="bb39c-123">Driver</span></span>

<span data-ttu-id="bb39c-124">O driver é chamado [dotnet](dotnet.md) e tem duas responsabilidades, executar um [aplicativo dependente da estrutura](../deploying/index.md) ou executar um comando.</span><span class="sxs-lookup"><span data-stu-id="bb39c-124">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="bb39c-125">Para executar um aplicativo dependente da estrutura, especifique o aplicativo após o driver, por exemplo, `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="bb39c-125">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="bb39c-126">Ao executar o comando na pasta onde está a DLL do aplicativo, basta executar `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="bb39c-126">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="bb39c-127">Se você quiser usar uma versão específica do tempo de execução do .NET, use a `--fx-version <VERSION>` opção (consulte a referência de [comando dotnet](dotnet.md) ).</span><span class="sxs-lookup"><span data-stu-id="bb39c-127">If you want to use a specific version of the .NET Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="bb39c-128">Quando você fornece um comando para o driver, `dotnet.exe` inicia o processo de execução do comando da CLI.</span><span class="sxs-lookup"><span data-stu-id="bb39c-128">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="bb39c-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb39c-129">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="bb39c-130">Primeiro, o driver determina a versão do SDK a ser usada.</span><span class="sxs-lookup"><span data-stu-id="bb39c-130">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="bb39c-131">Se não houver nenhum [global.jsno](global-json.md) arquivo, a versão mais recente do SDK disponível será usada.</span><span class="sxs-lookup"><span data-stu-id="bb39c-131">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="bb39c-132">Isso pode ser uma versão prévia ou estável, dependendo do que há de mais recente no computador.</span><span class="sxs-lookup"><span data-stu-id="bb39c-132">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="bb39c-133">Depois que a versão do SDK é determinada, ela executa o comando.</span><span class="sxs-lookup"><span data-stu-id="bb39c-133">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="bb39c-134">Comando</span><span class="sxs-lookup"><span data-stu-id="bb39c-134">Command</span></span>

<span data-ttu-id="bb39c-135">O comando executa uma ação.</span><span class="sxs-lookup"><span data-stu-id="bb39c-135">The command performs an action.</span></span> <span data-ttu-id="bb39c-136">Por exemplo, `dotnet build` compila código.</span><span class="sxs-lookup"><span data-stu-id="bb39c-136">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="bb39c-137">`dotnet publish` publica o código.</span><span class="sxs-lookup"><span data-stu-id="bb39c-137">`dotnet publish` publishes code.</span></span> <span data-ttu-id="bb39c-138">Os comandos são implementados como um aplicativo de console usando uma convenção `dotnet {command}`.</span><span class="sxs-lookup"><span data-stu-id="bb39c-138">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="bb39c-139">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bb39c-139">Arguments</span></span>

<span data-ttu-id="bb39c-140">Os argumentos que você passa na linha de comando são aqueles do comando invocado.</span><span class="sxs-lookup"><span data-stu-id="bb39c-140">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="bb39c-141">Por exemplo, quando você executa `dotnet publish my_app.csproj` o, o `my_app.csproj` argumento indica o projeto a ser publicado e é passado para o `publish` comando.</span><span class="sxs-lookup"><span data-stu-id="bb39c-141">For example, when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="bb39c-142">Opções</span><span class="sxs-lookup"><span data-stu-id="bb39c-142">Options</span></span>

<span data-ttu-id="bb39c-143">As opções que você passa na linha de comando são aquelas do comando invocado.</span><span class="sxs-lookup"><span data-stu-id="bb39c-143">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="bb39c-144">Por exemplo, quando você executa `dotnet publish --output /build_output` o, a `--output` opção e seu valor são passados para o `publish` comando.</span><span class="sxs-lookup"><span data-stu-id="bb39c-144">For example, when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb39c-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bb39c-145">See also</span></span>

- [<span data-ttu-id="bb39c-146">repositório do GitHub do dotnet/SDK</span><span class="sxs-lookup"><span data-stu-id="bb39c-146">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="bb39c-147">Guia de instalação do .NET</span><span class="sxs-lookup"><span data-stu-id="bb39c-147">.NET installation guide</span></span>](../install/windows.md)
