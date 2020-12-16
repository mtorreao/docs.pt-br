---
title: dotnet-ferramenta de diagnóstico do gcdump – CLI do .NET
description: Saiba como instalar e usar a ferramenta de CLI do dotnet-gcdump para coletar despejos de GC (coletor de lixo) de processos do .NET em tempo real usando o .NET EventPipe.
ms.date: 11/17/2020
ms.openlocfilehash: 02e1a7c5d86b582289672a027464aefd67a6f490
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593364"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="1a05e-103">Ferramenta de análise de heap (dotNet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="1a05e-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="1a05e-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="1a05e-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="1a05e-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="1a05e-105">Install</span></span>

<span data-ttu-id="1a05e-106">Há duas maneiras de baixar e instalar `dotnet-gcdump` :</span><span class="sxs-lookup"><span data-stu-id="1a05e-106">There are two ways to download and install `dotnet-gcdump`:</span></span>

- <span data-ttu-id="1a05e-107">**ferramenta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="1a05e-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="1a05e-108">Para instalar a versão de lançamento mais recente do `dotnet-gcdump` [pacote NuGet](https://www.nuget.org/packages/dotnet-gcdump), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="1a05e-108">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-gcdump
  ```

- <span data-ttu-id="1a05e-109">**Download direto:**</span><span class="sxs-lookup"><span data-stu-id="1a05e-109">**Direct download:**</span></span>

  <span data-ttu-id="1a05e-110">Baixe o executável da ferramenta que corresponde à sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="1a05e-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="1a05e-111">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="1a05e-111">OS</span></span>  | <span data-ttu-id="1a05e-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="1a05e-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="1a05e-113">Windows</span><span class="sxs-lookup"><span data-stu-id="1a05e-113">Windows</span></span> | <span data-ttu-id="1a05e-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [ARM](https://aka.ms/dotnet-gcdump/win-arm) \| [ARM-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="1a05e-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span></span> |
  | <span data-ttu-id="1a05e-115">macOS</span><span class="sxs-lookup"><span data-stu-id="1a05e-115">macOS</span></span>   | [<span data-ttu-id="1a05e-116">x64</span><span class="sxs-lookup"><span data-stu-id="1a05e-116">x64</span></span>](https://aka.ms/dotnet-gcdump/osx-x64) |
  | <span data-ttu-id="1a05e-117">Linux</span><span class="sxs-lookup"><span data-stu-id="1a05e-117">Linux</span></span>   | <span data-ttu-id="1a05e-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [ARM](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [MUSL-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [MUSL-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="1a05e-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="1a05e-119">Sinopse</span><span class="sxs-lookup"><span data-stu-id="1a05e-119">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="1a05e-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="1a05e-120">Description</span></span>

<span data-ttu-id="1a05e-121">A `dotnet-gcdump` ferramenta global coleta despejos GC (coletor de lixo) de processos do Live .NET usando o [EventPipe](./eventpipe.md).</span><span class="sxs-lookup"><span data-stu-id="1a05e-121">The `dotnet-gcdump` global tool collects GC (Garbage Collector) dumps of live .NET processes using [EventPipe](./eventpipe.md).</span></span> <span data-ttu-id="1a05e-122">Os despejos de GC são criados disparando um GC no processo de destino, ativando eventos especiais e regenerando o grafo de raízes de objeto a partir do fluxo de eventos.</span><span class="sxs-lookup"><span data-stu-id="1a05e-122">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="1a05e-123">Esse processo permite que os despejos de GC sejam coletados enquanto o processo está em execução e com sobrecarga mínima.</span><span class="sxs-lookup"><span data-stu-id="1a05e-123">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="1a05e-124">Esses despejos são úteis para vários cenários:</span><span class="sxs-lookup"><span data-stu-id="1a05e-124">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="1a05e-125">Comparando o número de objetos no heap em vários pontos no tempo.</span><span class="sxs-lookup"><span data-stu-id="1a05e-125">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="1a05e-126">Análise de raízes de objetos (respondendo a perguntas como "o que ainda tem uma referência a esse tipo?").</span><span class="sxs-lookup"><span data-stu-id="1a05e-126">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="1a05e-127">Coletando estatísticas gerais sobre as contagens de objetos no heap.</span><span class="sxs-lookup"><span data-stu-id="1a05e-127">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="1a05e-128">Exibir o despejo de GC capturado de dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="1a05e-128">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="1a05e-129">No Windows, `.gcdump` os arquivos podem ser exibidos no [Perfview](https://github.com/microsoft/perfview) para análise ou no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1a05e-129">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="1a05e-130">Atualmente, não há nenhuma maneira de abrir um `.gcdump` em plataformas não Windows.</span><span class="sxs-lookup"><span data-stu-id="1a05e-130">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="1a05e-131">Você pode coletar vários `.gcdump` s e abri-los simultaneamente no Visual Studio para obter uma experiência de comparação.</span><span class="sxs-lookup"><span data-stu-id="1a05e-131">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="1a05e-132">Opções</span><span class="sxs-lookup"><span data-stu-id="1a05e-132">Options</span></span>

- **`--version`**

  <span data-ttu-id="1a05e-133">Exibe a versão do `dotnet-gcdump` Utilitário do.</span><span class="sxs-lookup"><span data-stu-id="1a05e-133">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="1a05e-134">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="1a05e-134">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="1a05e-135">Coleta um despejo de GC de um processo em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="1a05e-135">Collects a GC dump from a currently running process.</span></span>

> [!WARNING]
> <span data-ttu-id="1a05e-136">Para percorrer o heap de GC, esse comando dispara uma coleta de lixo de geração 2 (completa), que pode suspender o tempo de execução por um longo tempo, especialmente quando o heap de GC for grande.</span><span class="sxs-lookup"><span data-stu-id="1a05e-136">To walk the GC heap, this command triggers a generation 2 (full) garbage collection, which can suspend the runtime for a long time, especially when the GC heap is large.</span></span> <span data-ttu-id="1a05e-137">Não use esse comando em ambientes sensíveis ao desempenho quando o heap de GC for grande.</span><span class="sxs-lookup"><span data-stu-id="1a05e-137">Don't use this command in performance-sensitive environments when the GC heap is large.</span></span>

### <a name="synopsis"></a><span data-ttu-id="1a05e-138">Sinopse</span><span class="sxs-lookup"><span data-stu-id="1a05e-138">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="1a05e-139">Opções</span><span class="sxs-lookup"><span data-stu-id="1a05e-139">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="1a05e-140">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="1a05e-140">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="1a05e-141">A ID do processo para coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="1a05e-141">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="1a05e-142">O caminho onde os despejos de GC coletados devem ser gravados.</span><span class="sxs-lookup"><span data-stu-id="1a05e-142">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="1a05e-143">O padrão é *. \\ AAAAMMDD \_ HHMMSS \_ \<pid> . gcdump*.</span><span class="sxs-lookup"><span data-stu-id="1a05e-143">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="1a05e-144">Gere o log durante a coleta do despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="1a05e-144">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="1a05e-145">Desistir da coleta do despejo do GC se levar mais tempo do que esse número de segundos.</span><span class="sxs-lookup"><span data-stu-id="1a05e-145">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="1a05e-146">O valor padrão é 30.</span><span class="sxs-lookup"><span data-stu-id="1a05e-146">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="1a05e-147">O nome do processo do qual coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="1a05e-147">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="1a05e-148">Lista os processos dotnet para os quais os despejos de GC podem ser coletados.</span><span class="sxs-lookup"><span data-stu-id="1a05e-148">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="1a05e-149">Sinopse</span><span class="sxs-lookup"><span data-stu-id="1a05e-149">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="1a05e-150">Gere um relatório de um despejo GC gerado anteriormente ou de um processo em execução e grave no `stdout` .</span><span class="sxs-lookup"><span data-stu-id="1a05e-150">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="1a05e-151">Sinopse</span><span class="sxs-lookup"><span data-stu-id="1a05e-151">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="1a05e-152">Opções</span><span class="sxs-lookup"><span data-stu-id="1a05e-152">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="1a05e-153">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="1a05e-153">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="1a05e-154">A ID do processo para coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="1a05e-154">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="1a05e-155">O tipo de relatório a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="1a05e-155">The type of report to generate.</span></span> <span data-ttu-id="1a05e-156">Opções disponíveis: heapstat (padrão).</span><span class="sxs-lookup"><span data-stu-id="1a05e-156">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="1a05e-157">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="1a05e-157">Troubleshoot</span></span>

- <span data-ttu-id="1a05e-158">Não há nenhuma informação de tipo no gcdump.</span><span class="sxs-lookup"><span data-stu-id="1a05e-158">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="1a05e-159">Antes do .NET Core 3,1, houve um problema em que um cache de tipo não foi limpo entre gcdumps quando eles eram invocados com EventPipe.</span><span class="sxs-lookup"><span data-stu-id="1a05e-159">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="1a05e-160">Isso resultou nos eventos necessários para determinar as informações de tipo que não estão sendo enviadas para o segundo e o gcdumps subsequente.</span><span class="sxs-lookup"><span data-stu-id="1a05e-160">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="1a05e-161">Isso foi corrigido no .NET Core 3,1-Preview2.</span><span class="sxs-lookup"><span data-stu-id="1a05e-161">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="1a05e-162">Os tipos COM e estáticos não estão no despejo de GC.</span><span class="sxs-lookup"><span data-stu-id="1a05e-162">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="1a05e-163">Antes do .NET Core 3,1-Preview2, houve um problema em que os tipos static e COM não eram enviados quando o despejo de GC era invocado via EventPipe.</span><span class="sxs-lookup"><span data-stu-id="1a05e-163">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="1a05e-164">Isso foi corrigido no .NET Core 3,1-Preview2.</span><span class="sxs-lookup"><span data-stu-id="1a05e-164">This has been fixed in .NET Core 3.1-preview2.</span></span>
