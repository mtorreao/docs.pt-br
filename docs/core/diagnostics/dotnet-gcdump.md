---
title: dotnet-ferramenta de diagnóstico do gcdump – CLI do .NET
description: Saiba como instalar e usar a ferramenta de CLI do dotnet-gcdump para coletar despejos de GC (coletor de lixo) de processos do .NET em tempo real usando o .NET EventPipe.
ms.date: 11/17/2020
ms.openlocfilehash: 59de1845ada9e5bdd0b24bf4312517283324ce94
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826034"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="3e7c3-103">Ferramenta de análise de heap (dotNet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="3e7c3-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="3e7c3-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="3e7c3-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="3e7c3-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="3e7c3-105">Install</span></span>

<span data-ttu-id="3e7c3-106">Há duas maneiras de baixar e instalar `dotnet-gcdump` :</span><span class="sxs-lookup"><span data-stu-id="3e7c3-106">There are two ways to download and install `dotnet-gcdump`:</span></span>

- <span data-ttu-id="3e7c3-107">**ferramenta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="3e7c3-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="3e7c3-108">Para instalar a versão de lançamento mais recente do `dotnet-gcdump` [pacote NuGet](https://www.nuget.org/packages/dotnet-gcdump), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="3e7c3-108">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-gcdump
  ```

- <span data-ttu-id="3e7c3-109">**Download direto:**</span><span class="sxs-lookup"><span data-stu-id="3e7c3-109">**Direct download:**</span></span>

  <span data-ttu-id="3e7c3-110">Baixe o executável da ferramenta que corresponde à sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="3e7c3-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="3e7c3-111">SO</span><span class="sxs-lookup"><span data-stu-id="3e7c3-111">OS</span></span>  | <span data-ttu-id="3e7c3-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="3e7c3-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="3e7c3-113">Windows</span><span class="sxs-lookup"><span data-stu-id="3e7c3-113">Windows</span></span> | <span data-ttu-id="3e7c3-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [ARM](https://aka.ms/dotnet-gcdump/win-arm) \| [ARM-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="3e7c3-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span></span> |
  | <span data-ttu-id="3e7c3-115">macOS</span><span class="sxs-lookup"><span data-stu-id="3e7c3-115">macOS</span></span>   | [<span data-ttu-id="3e7c3-116">x64</span><span class="sxs-lookup"><span data-stu-id="3e7c3-116">x64</span></span>](https://aka.ms/dotnet-gcdump/osx-x64) |
  | <span data-ttu-id="3e7c3-117">Linux</span><span class="sxs-lookup"><span data-stu-id="3e7c3-117">Linux</span></span>   | <span data-ttu-id="3e7c3-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [ARM](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [MUSL-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [MUSL-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="3e7c3-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="3e7c3-119">Sinopse</span><span class="sxs-lookup"><span data-stu-id="3e7c3-119">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="3e7c3-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="3e7c3-120">Description</span></span>

<span data-ttu-id="3e7c3-121">A `dotnet-gcdump` ferramenta global coleta despejos GC (coletor de lixo) de processos do Live .NET usando o [EventPipe](./eventpipe.md).</span><span class="sxs-lookup"><span data-stu-id="3e7c3-121">The `dotnet-gcdump` global tool collects GC (Garbage Collector) dumps of live .NET processes using [EventPipe](./eventpipe.md).</span></span> <span data-ttu-id="3e7c3-122">Os despejos de GC são criados disparando um GC no processo de destino, ativando eventos especiais e regenerando o grafo de raízes de objeto a partir do fluxo de eventos.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-122">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="3e7c3-123">Esse processo permite que os despejos de GC sejam coletados enquanto o processo está em execução e com sobrecarga mínima.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-123">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="3e7c3-124">Esses despejos são úteis para vários cenários:</span><span class="sxs-lookup"><span data-stu-id="3e7c3-124">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="3e7c3-125">Comparando o número de objetos no heap em vários pontos no tempo.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-125">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="3e7c3-126">Análise de raízes de objetos (respondendo a perguntas como "o que ainda tem uma referência a esse tipo?").</span><span class="sxs-lookup"><span data-stu-id="3e7c3-126">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="3e7c3-127">Coletando estatísticas gerais sobre as contagens de objetos no heap.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-127">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="3e7c3-128">Exibir o despejo de GC capturado de dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="3e7c3-128">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="3e7c3-129">No Windows, `.gcdump` os arquivos podem ser exibidos no [Perfview](https://github.com/microsoft/perfview) para análise ou no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-129">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="3e7c3-130">Atualmente, não há nenhuma maneira de abrir um `.gcdump` em plataformas não Windows.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-130">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="3e7c3-131">Você pode coletar vários `.gcdump` s e abri-los simultaneamente no Visual Studio para obter uma experiência de comparação.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-131">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="3e7c3-132">Opções</span><span class="sxs-lookup"><span data-stu-id="3e7c3-132">Options</span></span>

- **`--version`**

  <span data-ttu-id="3e7c3-133">Exibe a versão do `dotnet-gcdump` Utilitário do.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-133">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3e7c3-134">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-134">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="3e7c3-135">Coleta um despejo de GC de um processo em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-135">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3e7c3-136">Sinopse</span><span class="sxs-lookup"><span data-stu-id="3e7c3-136">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="3e7c3-137">Opções</span><span class="sxs-lookup"><span data-stu-id="3e7c3-137">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="3e7c3-138">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-138">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="3e7c3-139">A ID do processo para coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-139">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="3e7c3-140">O caminho onde os despejos de GC coletados devem ser gravados.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-140">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="3e7c3-141">O padrão é *. \\ AAAAMMDD \_ HHMMSS \_ \<pid> . gcdump*.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-141">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="3e7c3-142">Gere o log durante a coleta do despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-142">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="3e7c3-143">Desistir da coleta do despejo do GC se levar mais tempo do que esse número de segundos.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-143">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="3e7c3-144">O valor padrão é 30.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-144">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="3e7c3-145">O nome do processo do qual coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-145">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="3e7c3-146">Lista os processos dotnet para os quais os despejos de GC podem ser coletados.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-146">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3e7c3-147">Sinopse</span><span class="sxs-lookup"><span data-stu-id="3e7c3-147">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="3e7c3-148">Gere um relatório de um despejo GC gerado anteriormente ou de um processo em execução e grave no `stdout` .</span><span class="sxs-lookup"><span data-stu-id="3e7c3-148">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3e7c3-149">Sinopse</span><span class="sxs-lookup"><span data-stu-id="3e7c3-149">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="3e7c3-150">Opções</span><span class="sxs-lookup"><span data-stu-id="3e7c3-150">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="3e7c3-151">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-151">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="3e7c3-152">A ID do processo para coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-152">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="3e7c3-153">O tipo de relatório a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-153">The type of report to generate.</span></span> <span data-ttu-id="3e7c3-154">Opções disponíveis: heapstat (padrão).</span><span class="sxs-lookup"><span data-stu-id="3e7c3-154">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="3e7c3-155">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="3e7c3-155">Troubleshoot</span></span>

- <span data-ttu-id="3e7c3-156">Não há nenhuma informação de tipo no gcdump.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-156">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="3e7c3-157">Antes do .NET Core 3,1, houve um problema em que um cache de tipo não foi limpo entre gcdumps quando eles eram invocados com EventPipe.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-157">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="3e7c3-158">Isso resultou nos eventos necessários para determinar as informações de tipo que não estão sendo enviadas para o segundo e o gcdumps subsequente.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-158">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="3e7c3-159">Isso foi corrigido no .NET Core 3,1-Preview2.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-159">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="3e7c3-160">Os tipos COM e estáticos não estão no despejo de GC.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-160">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="3e7c3-161">Antes do .NET Core 3,1-Preview2, houve um problema em que os tipos static e COM não eram enviados quando o despejo de GC era invocado via EventPipe.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-161">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="3e7c3-162">Isso foi corrigido no .NET Core 3,1-Preview2.</span><span class="sxs-lookup"><span data-stu-id="3e7c3-162">This has been fixed in .NET Core 3.1-preview2.</span></span>
