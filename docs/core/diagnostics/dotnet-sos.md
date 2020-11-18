---
title: dotnet – ferramenta de diagnóstico do SOS-CLI do .NET
description: Saiba como instalar e usar a ferramenta dotnet-SOS CLI para gerenciar a extensão do depurador SOS, que é usada com depuradores nativos no Windows e no Linux.
ms.date: 11/17/2020
ms.openlocfilehash: 59512c42a778f68bb3cd092dc854dcc727fd2881
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825436"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="ed61d-103">Instalador do SOS (dotNet-SOS)</span><span class="sxs-lookup"><span data-stu-id="ed61d-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="ed61d-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 2,1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="ed61d-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="ed61d-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="ed61d-105">Install</span></span>

<span data-ttu-id="ed61d-106">Há duas maneiras de baixar e instalar `dotnet-sos` :</span><span class="sxs-lookup"><span data-stu-id="ed61d-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="ed61d-107">**ferramenta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="ed61d-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="ed61d-108">Para instalar a versão de lançamento mais recente do `dotnet-sos` [pacote NuGet](https://www.nuget.org/packages/dotnet-sos), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="ed61d-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="ed61d-109">**Download direto:**</span><span class="sxs-lookup"><span data-stu-id="ed61d-109">**Direct download:**</span></span>

  <span data-ttu-id="ed61d-110">Baixe o executável da ferramenta que corresponde à sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="ed61d-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="ed61d-111">SO</span><span class="sxs-lookup"><span data-stu-id="ed61d-111">OS</span></span>  | <span data-ttu-id="ed61d-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="ed61d-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="ed61d-113">Windows</span><span class="sxs-lookup"><span data-stu-id="ed61d-113">Windows</span></span> | <span data-ttu-id="ed61d-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [ARM](https://aka.ms/dotnet-sos/win-arm) \| [ARM-x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="ed61d-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="ed61d-115">macOS</span><span class="sxs-lookup"><span data-stu-id="ed61d-115">macOS</span></span>   | [<span data-ttu-id="ed61d-116">x64</span><span class="sxs-lookup"><span data-stu-id="ed61d-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="ed61d-117">Linux</span><span class="sxs-lookup"><span data-stu-id="ed61d-117">Linux</span></span>   | <span data-ttu-id="ed61d-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [ARM](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [MUSL-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [MUSL-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="ed61d-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="ed61d-119">Sinopse</span><span class="sxs-lookup"><span data-stu-id="ed61d-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="ed61d-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="ed61d-120">Description</span></span>

<span data-ttu-id="ed61d-121">A `dotnet-sos` ferramenta global instala a [extensão do depurador SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) , permitindo a [inspeção do estado do .NET Core gerenciado](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) por meio de depuradores nativos como WinDbg/CDB no Windows e Lldb no Linux e no MacOS.</span><span class="sxs-lookup"><span data-stu-id="ed61d-121">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="ed61d-122">As versões recentes do depurador do Windows (>= versão 10.0.18317.1001 do WinDbg ou do CDB) carregarão o SOS automaticamente da Galeria de extensões da Microsoft, portanto, instalar o SOS por meio da `dotnet-sos` ferramenta só será necessário no Linux e no MacOS ou no Windows se estiver usando ferramentas de depuração mais antigas.</span><span class="sxs-lookup"><span data-stu-id="ed61d-122">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="ed61d-123">Opções</span><span class="sxs-lookup"><span data-stu-id="ed61d-123">Options</span></span>

- **`--version`**

  <span data-ttu-id="ed61d-124">Exibe informações de versão.</span><span class="sxs-lookup"><span data-stu-id="ed61d-124">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ed61d-125">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="ed61d-125">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="ed61d-126">dotnet – instalação do SOS</span><span class="sxs-lookup"><span data-stu-id="ed61d-126">dotnet-sos install</span></span>

<span data-ttu-id="ed61d-127">Instala a [extensão SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) localmente para depurar processos do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ed61d-127">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="ed61d-128">No macOS e Linux, o arquivo. lldbinit será atualizado para que a extensão seja carregada automaticamente na inicialização do lldb.</span><span class="sxs-lookup"><span data-stu-id="ed61d-128">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="ed61d-129">Se estiver instalando o SOS no Windows com as ferramentas de depuração mais antigas (< versão 10.0.18317.1001), será necessário carregar manualmente a extensão no WinDbg ou no CDB executando `.load %USERPROFILE%\.dotnet\sos\sos.dll` no depurador.</span><span class="sxs-lookup"><span data-stu-id="ed61d-129">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ed61d-130">Sinopse</span><span class="sxs-lookup"><span data-stu-id="ed61d-130">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="ed61d-131">dotnet – desinstalação do SOS</span><span class="sxs-lookup"><span data-stu-id="ed61d-131">dotnet-sos uninstall</span></span>

<span data-ttu-id="ed61d-132">Desinstala a [extensão SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) e, se estiver no Linux ou no MacOS, o removerá da configuração do lldb.</span><span class="sxs-lookup"><span data-stu-id="ed61d-132">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ed61d-133">Sinopse</span><span class="sxs-lookup"><span data-stu-id="ed61d-133">Synopsis</span></span>

```console
dotnet-sos uninstall
```
