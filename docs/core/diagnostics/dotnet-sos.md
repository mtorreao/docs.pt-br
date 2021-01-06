---
title: dotnet – ferramenta de diagnóstico do SOS-CLI do .NET
description: Saiba como instalar e usar a ferramenta dotnet-SOS CLI para gerenciar a extensão do depurador SOS, que é usada com depuradores nativos no Windows e no Linux.
ms.date: 11/17/2020
ms.openlocfilehash: 09e8228c47bdc632bccf3c9ad2296d55fe420060
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/24/2020
ms.locfileid: "97765001"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="d2c53-103">Instalador do SOS (dotNet-SOS)</span><span class="sxs-lookup"><span data-stu-id="d2c53-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="d2c53-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 2,1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="d2c53-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="d2c53-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="d2c53-105">Install</span></span>

<span data-ttu-id="d2c53-106">Há duas maneiras de baixar e instalar `dotnet-sos` :</span><span class="sxs-lookup"><span data-stu-id="d2c53-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="d2c53-107">**ferramenta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="d2c53-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="d2c53-108">Para instalar a versão de lançamento mais recente do `dotnet-sos` [pacote NuGet](https://www.nuget.org/packages/dotnet-sos), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="d2c53-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="d2c53-109">**Download direto:**</span><span class="sxs-lookup"><span data-stu-id="d2c53-109">**Direct download:**</span></span>

  <span data-ttu-id="d2c53-110">Baixe o executável da ferramenta que corresponde à sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="d2c53-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="d2c53-111">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="d2c53-111">OS</span></span>  | <span data-ttu-id="d2c53-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="d2c53-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="d2c53-113">Windows</span><span class="sxs-lookup"><span data-stu-id="d2c53-113">Windows</span></span> | <span data-ttu-id="d2c53-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [ARM](https://aka.ms/dotnet-sos/win-arm) \| [ARM-x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="d2c53-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="d2c53-115">macOS</span><span class="sxs-lookup"><span data-stu-id="d2c53-115">macOS</span></span>   | [<span data-ttu-id="d2c53-116">x64</span><span class="sxs-lookup"><span data-stu-id="d2c53-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="d2c53-117">Linux</span><span class="sxs-lookup"><span data-stu-id="d2c53-117">Linux</span></span>   | <span data-ttu-id="d2c53-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [ARM](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [MUSL-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [MUSL-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="d2c53-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="d2c53-119">Sinopse</span><span class="sxs-lookup"><span data-stu-id="d2c53-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="d2c53-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="d2c53-120">Description</span></span>

<span data-ttu-id="d2c53-121">A `dotnet-sos` ferramenta global instala a [extensão do depurador SOS](sos-debugging-extension.md).</span><span class="sxs-lookup"><span data-stu-id="d2c53-121">The `dotnet-sos` global tool installs the [SOS debugger extension](sos-debugging-extension.md).</span></span> <span data-ttu-id="d2c53-122">Essa extensão permite inspecionar o estado do .NET Core gerenciado a partir de depuradores nativos, como lldb e WinDbg.</span><span class="sxs-lookup"><span data-stu-id="d2c53-122">This extension lets you inspect managed .NET Core state from native debuggers like lldb and windbg.</span></span>

> [!NOTE]
> <span data-ttu-id="d2c53-123">A instalação do SOS por meio da `dotnet-sos` ferramenta só é necessária no Linux ou no MacOS.</span><span class="sxs-lookup"><span data-stu-id="d2c53-123">Installing SOS via the `dotnet-sos` tool is only needed on Linux or macOS.</span></span>  <span data-ttu-id="d2c53-124">Ele também pode ser necessário no Windows se você estiver usando ferramentas de depuração mais antigas.</span><span class="sxs-lookup"><span data-stu-id="d2c53-124">It may also be needed on Windows if you're using older debugging tools.</span></span> <span data-ttu-id="d2c53-125">As versões recentes do [depurador do Windows](/windows-hardware/drivers/debugger/debugger-download-tools) (>= versão 10.0.18317.1001 do WinDbg ou do CDB) carregam o SOS automaticamente da Galeria de extensões da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d2c53-125">Recent versions of the [Windows Debugger](/windows-hardware/drivers/debugger/debugger-download-tools) (>= version 10.0.18317.1001 of WinDbg or cdb) load SOS automatically from the Microsoft extension gallery.</span></span>  

## <a name="options"></a><span data-ttu-id="d2c53-126">Opções</span><span class="sxs-lookup"><span data-stu-id="d2c53-126">Options</span></span>

- **`--version`**

  <span data-ttu-id="d2c53-127">Exibe informações de versão.</span><span class="sxs-lookup"><span data-stu-id="d2c53-127">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d2c53-128">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d2c53-128">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="d2c53-129">dotnet – instalação do SOS</span><span class="sxs-lookup"><span data-stu-id="d2c53-129">dotnet-sos install</span></span>

<span data-ttu-id="d2c53-130">Instala a [extensão SOS](sos-debugging-extension.md) localmente para depurar processos do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d2c53-130">Installs the [SOS extension](sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="d2c53-131">No macOS e Linux, o arquivo *. lldbinit* será atualizado para que a extensão seja carregada automaticamente na inicialização do lldb.</span><span class="sxs-lookup"><span data-stu-id="d2c53-131">On macOS and Linux, the *.lldbinit* file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="d2c53-132">Se você estiver instalando o SOS no Windows com as ferramentas de depuração mais antigas (antes da versão 10.0.18317.1001), será necessário carregar manualmente a extensão no WinDbg ou no CDB executando `.load %USERPROFILE%\.dotnet\sos\sos.dll` no depurador.</span><span class="sxs-lookup"><span data-stu-id="d2c53-132">If you're installing SOS on Windows with older debugging tools (prior to version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d2c53-133">Sinopse</span><span class="sxs-lookup"><span data-stu-id="d2c53-133">Synopsis</span></span>

```console
dotnet-sos install [--architecture <arch>]
```

### <a name="options"></a><span data-ttu-id="d2c53-134">Opções</span><span class="sxs-lookup"><span data-stu-id="d2c53-134">Options</span></span>

- **`--architecture <arch>`**

  <span data-ttu-id="d2c53-135">Especifica a arquitetura do processador dos binários SOS a serem instalados.</span><span class="sxs-lookup"><span data-stu-id="d2c53-135">Specifies the processor architecture of the SOS binaries to install.</span></span> <span data-ttu-id="d2c53-136">Por padrão, `dotnet-sos` o instala a arquitetura do computador host.</span><span class="sxs-lookup"><span data-stu-id="d2c53-136">By default, `dotnet-sos` installs the architecture of the host machine.</span></span> <span data-ttu-id="d2c53-137">Use essa opção quando quiser instalar o SOS para uma arquitetura diferente da arquitetura de host dotnet.</span><span class="sxs-lookup"><span data-stu-id="d2c53-137">Use this option when you want to install SOS for an architecture that's different from the dotnet host architecture.</span></span> <span data-ttu-id="d2c53-138">Por exemplo, se você estiver executando binários Arm32 de um host Arm64, será necessário instalar o SOS com o `dotnet-sos install --architecture Arm` .</span><span class="sxs-lookup"><span data-stu-id="d2c53-138">For example, if you're running Arm32 binaries from an Arm64 host, you will need to install SOS with `dotnet-sos install --architecture Arm`.</span></span>

  <span data-ttu-id="d2c53-139">As arquiteturas a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="d2c53-139">The following architectures are available:</span></span>

  - `Arm`
  - `Arm64`
  - `X86`
  - `X64`

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="d2c53-140">dotnet – desinstalação do SOS</span><span class="sxs-lookup"><span data-stu-id="d2c53-140">dotnet-sos uninstall</span></span>

<span data-ttu-id="d2c53-141">Desinstala a [extensão SOS](sos-debugging-extension.md) e, no Linux e MacOS, remove-a da configuração do lldb.</span><span class="sxs-lookup"><span data-stu-id="d2c53-141">Uninstalls the [SOS extension](sos-debugging-extension.md) and, on Linux and macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d2c53-142">Sinopse</span><span class="sxs-lookup"><span data-stu-id="d2c53-142">Synopsis</span></span>

```console
dotnet-sos uninstall
```
