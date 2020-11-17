---
title: dotnet-gcdump-.NET Core
description: Instalando e usando a ferramenta de linha de comando dotnet-gcdump.
ms.date: 07/26/2020
ms.openlocfilehash: c73afae9ecdfa907e9655634a0ac355cab4ef558
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687610"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="2a462-103">Ferramenta de análise de heap (dotNet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="2a462-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="2a462-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="2a462-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install-dotnet-gcdump"></a><span data-ttu-id="2a462-105">Instalar dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="2a462-105">Install dotnet-gcdump</span></span>

<span data-ttu-id="2a462-106">Para instalar a versão de lançamento mais recente do `dotnet-gcdump` [pacote NuGet](https://www.nuget.org/packages/dotnet-gcdump), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="2a462-106">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a><span data-ttu-id="2a462-107">Sinopse</span><span class="sxs-lookup"><span data-stu-id="2a462-107">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="2a462-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a462-108">Description</span></span>

<span data-ttu-id="2a462-109">A `dotnet-gcdump` ferramenta global coleta despejos GC (coletor de lixo) de processos do Live .NET usando o [EventPipe](./eventpipe.md).</span><span class="sxs-lookup"><span data-stu-id="2a462-109">The `dotnet-gcdump` global tool collects GC (Garbage Collector) dumps of live .NET processes using [EventPipe](./eventpipe.md).</span></span> <span data-ttu-id="2a462-110">Os despejos de GC são criados disparando um GC no processo de destino, ativando eventos especiais e regenerando o grafo de raízes de objeto a partir do fluxo de eventos.</span><span class="sxs-lookup"><span data-stu-id="2a462-110">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="2a462-111">Esse processo permite que os despejos de GC sejam coletados enquanto o processo está em execução e com sobrecarga mínima.</span><span class="sxs-lookup"><span data-stu-id="2a462-111">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="2a462-112">Esses despejos são úteis para vários cenários:</span><span class="sxs-lookup"><span data-stu-id="2a462-112">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="2a462-113">Comparando o número de objetos no heap em vários pontos no tempo.</span><span class="sxs-lookup"><span data-stu-id="2a462-113">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="2a462-114">Análise de raízes de objetos (respondendo a perguntas como "o que ainda tem uma referência a esse tipo?").</span><span class="sxs-lookup"><span data-stu-id="2a462-114">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="2a462-115">Coletando estatísticas gerais sobre as contagens de objetos no heap.</span><span class="sxs-lookup"><span data-stu-id="2a462-115">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="2a462-116">Exibir o despejo de GC capturado de dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="2a462-116">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="2a462-117">No Windows, `.gcdump` os arquivos podem ser exibidos no [Perfview](https://github.com/microsoft/perfview) para análise ou no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2a462-117">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="2a462-118">Atualmente, não há nenhuma maneira de abrir um `.gcdump` em plataformas não Windows.</span><span class="sxs-lookup"><span data-stu-id="2a462-118">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="2a462-119">Você pode coletar vários `.gcdump` s e abri-los simultaneamente no Visual Studio para obter uma experiência de comparação.</span><span class="sxs-lookup"><span data-stu-id="2a462-119">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="2a462-120">Opções</span><span class="sxs-lookup"><span data-stu-id="2a462-120">Options</span></span>

- **`--version`**

  <span data-ttu-id="2a462-121">Exibe a versão do `dotnet-gcdump` Utilitário do.</span><span class="sxs-lookup"><span data-stu-id="2a462-121">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2a462-122">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2a462-122">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="2a462-123">Coleta um despejo de GC de um processo em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="2a462-123">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="2a462-124">Sinopse</span><span class="sxs-lookup"><span data-stu-id="2a462-124">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="2a462-125">Opções</span><span class="sxs-lookup"><span data-stu-id="2a462-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="2a462-126">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2a462-126">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="2a462-127">A ID do processo para coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="2a462-127">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="2a462-128">O caminho onde os despejos de GC coletados devem ser gravados.</span><span class="sxs-lookup"><span data-stu-id="2a462-128">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="2a462-129">O padrão é *. \\ AAAAMMDD \_ HHMMSS \_ \<pid> . gcdump*.</span><span class="sxs-lookup"><span data-stu-id="2a462-129">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="2a462-130">Gere o log durante a coleta do despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="2a462-130">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="2a462-131">Desistir da coleta do despejo do GC se levar mais tempo do que esse número de segundos.</span><span class="sxs-lookup"><span data-stu-id="2a462-131">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="2a462-132">O valor padrão é 30.</span><span class="sxs-lookup"><span data-stu-id="2a462-132">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="2a462-133">O nome do processo do qual coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="2a462-133">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="2a462-134">Lista os processos dotnet para os quais os despejos de GC podem ser coletados.</span><span class="sxs-lookup"><span data-stu-id="2a462-134">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="2a462-135">Sinopse</span><span class="sxs-lookup"><span data-stu-id="2a462-135">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="2a462-136">Gere um relatório de um despejo GC gerado anteriormente ou de um processo em execução e grave no `stdout` .</span><span class="sxs-lookup"><span data-stu-id="2a462-136">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="2a462-137">Sinopse</span><span class="sxs-lookup"><span data-stu-id="2a462-137">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="2a462-138">Opções</span><span class="sxs-lookup"><span data-stu-id="2a462-138">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="2a462-139">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2a462-139">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="2a462-140">A ID do processo para coletar o despejo do GC.</span><span class="sxs-lookup"><span data-stu-id="2a462-140">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="2a462-141">O tipo de relatório a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="2a462-141">The type of report to generate.</span></span> <span data-ttu-id="2a462-142">Opções disponíveis: heapstat (padrão).</span><span class="sxs-lookup"><span data-stu-id="2a462-142">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="2a462-143">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="2a462-143">Troubleshoot</span></span>

- <span data-ttu-id="2a462-144">Não há nenhuma informação de tipo no gcdump.</span><span class="sxs-lookup"><span data-stu-id="2a462-144">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="2a462-145">Antes do .NET Core 3,1, houve um problema em que um cache de tipo não foi limpo entre gcdumps quando eles eram invocados com EventPipe.</span><span class="sxs-lookup"><span data-stu-id="2a462-145">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="2a462-146">Isso resultou nos eventos necessários para determinar as informações de tipo que não estão sendo enviadas para o segundo e o gcdumps subsequente.</span><span class="sxs-lookup"><span data-stu-id="2a462-146">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="2a462-147">Isso foi corrigido no .NET Core 3,1-Preview2.</span><span class="sxs-lookup"><span data-stu-id="2a462-147">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="2a462-148">Os tipos COM e estáticos não estão no despejo de GC.</span><span class="sxs-lookup"><span data-stu-id="2a462-148">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="2a462-149">Antes do .NET Core 3,1-Preview2, houve um problema em que os tipos static e COM não eram enviados quando o despejo de GC era invocado via EventPipe.</span><span class="sxs-lookup"><span data-stu-id="2a462-149">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="2a462-150">Isso foi corrigido no .NET Core 3,1-Preview2.</span><span class="sxs-lookup"><span data-stu-id="2a462-150">This has been fixed in .NET Core 3.1-preview2.</span></span>
