---
title: Visão geral das ferramentas de diagnóstico – .NET Core
description: Uma visão geral das ferramentas e das técnicas disponíveis para diagnosticar aplicativos .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: c43e661ad8c9f665151e0240bf6b54e61b9acfef
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031911"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="6c17d-103">Quais ferramentas de diagnóstico estão disponíveis no .NET Core?</span><span class="sxs-lookup"><span data-stu-id="6c17d-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="6c17d-104">O software nem sempre se comporta como esperado, mas o .NET Core tem ferramentas e APIs que ajudarão você a diagnosticar esses problemas de maneira rápida e eficaz.</span><span class="sxs-lookup"><span data-stu-id="6c17d-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="6c17d-105">Este artigo ajuda a identificar as diversas ferramentas de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="6c17d-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="6c17d-106">Depuradores gerenciados</span><span class="sxs-lookup"><span data-stu-id="6c17d-106">Managed debuggers</span></span>

<span data-ttu-id="6c17d-107">Os [depuradores gerenciados](managed-debuggers.md) permitem que você interaja com seu programa.</span><span class="sxs-lookup"><span data-stu-id="6c17d-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="6c17d-108">Pausar, executar incrementalmente, examinar e retomar fornecem informações sobre o comportamento do seu código.</span><span class="sxs-lookup"><span data-stu-id="6c17d-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="6c17d-109">Um depurador é a primeira opção para diagnosticar problemas funcionais que podem ser facilmente reproduzidos.</span><span class="sxs-lookup"><span data-stu-id="6c17d-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="6c17d-110">Registro em log e rastreamento</span><span class="sxs-lookup"><span data-stu-id="6c17d-110">Logging and tracing</span></span>

<span data-ttu-id="6c17d-111">O [registro em log e o rastreamento](logging-tracing.md) são técnicas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6c17d-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="6c17d-112">Eles se referem ao código de instrumentação para criar arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="6c17d-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="6c17d-113">Os arquivos registram os detalhes do que um programa faz.</span><span class="sxs-lookup"><span data-stu-id="6c17d-113">The files record the details of what a program does.</span></span> <span data-ttu-id="6c17d-114">Esses detalhes podem ser usados para diagnosticar os problemas mais complexos.</span><span class="sxs-lookup"><span data-stu-id="6c17d-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="6c17d-115">Quando aliados aos carimbos de data/hora, essas técnicas também são valiosas para as investigações de desempenho.</span><span class="sxs-lookup"><span data-stu-id="6c17d-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="6c17d-116">Teste de unidade</span><span class="sxs-lookup"><span data-stu-id="6c17d-116">Unit testing</span></span>

<span data-ttu-id="6c17d-117">O [teste de unidade](../testing/index.md) é um componente fundamental da integração e da implantação contínuas de software de alta qualidade.</span><span class="sxs-lookup"><span data-stu-id="6c17d-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="6c17d-118">Os testes de unidade são projetados para fornecer um aviso antecipado quando você interrompe algo.</span><span class="sxs-lookup"><span data-stu-id="6c17d-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="dumps"></a><span data-ttu-id="6c17d-119">Despejos</span><span class="sxs-lookup"><span data-stu-id="6c17d-119">Dumps</span></span>

<span data-ttu-id="6c17d-120">Um [despejo](./dumps.md) é um arquivo que contém um instantâneo do processo no momento da criação.</span><span class="sxs-lookup"><span data-stu-id="6c17d-120">A [dump](./dumps.md) is a file that contains a snapshot of the process at the time of creation.</span></span> <span data-ttu-id="6c17d-121">Eles podem ser úteis para examinar o estado do aplicativo para fins de depuração.</span><span class="sxs-lookup"><span data-stu-id="6c17d-121">These can be useful for examining the state of your application for debugging purposes.</span></span>

## <a name="collect-diagnostics-in-containers"></a><span data-ttu-id="6c17d-122">Coletar diagnósticos em contêineres</span><span class="sxs-lookup"><span data-stu-id="6c17d-122">Collect diagnostics in containers</span></span>

<span data-ttu-id="6c17d-123">As mesmas ferramentas de diagnóstico usadas em ambientes Linux não-contêineres também podem ser usadas para [coletar diagnósticos em contêineres](diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="6c17d-123">The same diagnostics tools that are used in non-containerized Linux environments can also be used to [collect diagnostics in containers](diagnostics-in-containers.md).</span></span> <span data-ttu-id="6c17d-124">Há apenas algumas alterações de uso necessárias para garantir que as ferramentas funcionem em um contêiner do Docker.</span><span class="sxs-lookup"><span data-stu-id="6c17d-124">There are just a few usage changes needed to make sure the tools work in a Docker container.</span></span>

## <a name="debug-linux-dumps"></a><span data-ttu-id="6c17d-125">Depurar despejos do Linux</span><span class="sxs-lookup"><span data-stu-id="6c17d-125">Debug Linux dumps</span></span>

<span data-ttu-id="6c17d-126">[Depurar despejos do Linux](debug-linux-dumps.md) explica como coletar e analisar despejos no Linux.</span><span class="sxs-lookup"><span data-stu-id="6c17d-126">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="6c17d-127">Ferramentas globais de diagnóstico do .NET Core</span><span class="sxs-lookup"><span data-stu-id="6c17d-127">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="6c17d-128">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="6c17d-128">dotnet-counters</span></span>

<span data-ttu-id="6c17d-129">[dotnet-os contadores](dotnet-counters.md) são uma ferramenta de monitoramento de desempenho para a investigação de desempenho e monitoramento de integridade de primeiro nível.</span><span class="sxs-lookup"><span data-stu-id="6c17d-129">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="6c17d-130">Ele observa os valores do contador de desempenho publicados por meio da <xref:System.Diagnostics.Tracing.EventCounter> API.</span><span class="sxs-lookup"><span data-stu-id="6c17d-130">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="6c17d-131">Por exemplo, você pode monitorar rapidamente coisas como o uso da CPU ou a taxa de exceções que estão sendo geradas em seu aplicativo .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6c17d-131">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="6c17d-132">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="6c17d-132">dotnet-dump</span></span>

<span data-ttu-id="6c17d-133">A ferramenta [dotnet-dump](dotnet-dump.md) é uma maneira de coletar e analisar despejos do Windows e do Linux Core sem um depurador nativo.</span><span class="sxs-lookup"><span data-stu-id="6c17d-133">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="6c17d-134">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="6c17d-134">dotnet-gcdump</span></span>

<span data-ttu-id="6c17d-135">A ferramenta [dotnet-gcdump](dotnet-gcdump.md) é uma maneira de coletar despejos de GC (coletor de lixo) de processos do .net em tempo real.</span><span class="sxs-lookup"><span data-stu-id="6c17d-135">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="6c17d-136">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="6c17d-136">dotnet-trace</span></span>

<span data-ttu-id="6c17d-137">O .NET Core inclui o que é chamado de `EventPipe` por meio do qual os dados de diagnóstico são expostos.</span><span class="sxs-lookup"><span data-stu-id="6c17d-137">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="6c17d-138">A ferramenta [dotnet-Trace](dotnet-trace.md) permite que você consuma dados de criação de perfil interessantes de seu aplicativo que podem ajudar em cenários em que você precisa ter a causa raiz dos aplicativos em execução lenta.</span><span class="sxs-lookup"><span data-stu-id="6c17d-138">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="6c17d-139">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="6c17d-139">dotnet-symbol</span></span>

<span data-ttu-id="6c17d-140">[dotnet-Symbol](dotnet-symbol.md) baixa arquivos (símbolos, DAC/DBI, arquivos de host, etc.) necessários para abrir um dump principal ou minidespejo.</span><span class="sxs-lookup"><span data-stu-id="6c17d-140">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="6c17d-141">Use essa ferramenta se precisar de símbolos e módulos para depurar um arquivo de despejo capturado em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="6c17d-141">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="6c17d-142">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="6c17d-142">dotnet-sos</span></span>

<span data-ttu-id="6c17d-143">[dotnet-SOS](dotnet-sos.md) é usado para instalar a [extensão de depuração SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) no Linux ou MacOS (ou no Windows, se estiver usando ferramentas de depuração mais antigas).</span><span class="sxs-lookup"><span data-stu-id="6c17d-143">[dotnet-sos](dotnet-sos.md) is used to install the [SOS debugging extension](../../framework/tools/sos-dll-sos-debugging-extension.md) on Linux or MacOS (or on Windows if using older debugging tools).</span></span>

### <a name="perfcollect"></a><span data-ttu-id="6c17d-144">PerfCollect</span><span class="sxs-lookup"><span data-stu-id="6c17d-144">PerfCollect</span></span>

<span data-ttu-id="6c17d-145">[PerfCollect](trace-perfcollect-lttng.md) é um script bash que você pode usar para coletar rastreamentos com `perf` e `LTTng` para uma análise de desempenho mais detalhada de aplicativos .net em execução em distribuições do Linux.</span><span class="sxs-lookup"><span data-stu-id="6c17d-145">[PerfCollect](trace-perfcollect-lttng.md) is a bash script you can use to collect traces with `perf` and `LTTng` for a more in-depth performance analysis of .NET apps running on Linux distributions.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="6c17d-146">Tutoriais de diagnóstico do .NET Core</span><span class="sxs-lookup"><span data-stu-id="6c17d-146">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="6c17d-147">Depurar um vazamento de memória</span><span class="sxs-lookup"><span data-stu-id="6c17d-147">Debug a memory leak</span></span>

<span data-ttu-id="6c17d-148">[Tutorial: Depurar um vazamento de memória](debug-memory-leak.md) percorre a localização de um vazamento de memória.</span><span class="sxs-lookup"><span data-stu-id="6c17d-148">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="6c17d-149">A ferramenta [dotnet-Counters](dotnet-counters.md) é usada para confirmar o vazamento e a ferramenta [dotnet-dump](dotnet-dump.md) é usada para diagnosticar o vazamento.</span><span class="sxs-lookup"><span data-stu-id="6c17d-149">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="6c17d-150">Depurar alto uso da CPU</span><span class="sxs-lookup"><span data-stu-id="6c17d-150">Debug high CPU usage</span></span>

<span data-ttu-id="6c17d-151">[Tutorial: Depurar alto uso da CPU](debug-highcpu.md) orienta você na investigação de alto uso da CPU.</span><span class="sxs-lookup"><span data-stu-id="6c17d-151">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="6c17d-152">Ele usa a ferramenta [dotnet-Counters](dotnet-counters.md) para confirmar o alto uso da CPU.</span><span class="sxs-lookup"><span data-stu-id="6c17d-152">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="6c17d-153">Em seguida, ele orienta você pelo uso [do trace for performance Analysis Utility ( `dotnet-trace` ) ou do](dotnet-trace.md) Linux `perf` para coletar e exibir o perfil de uso da CPU.</span><span class="sxs-lookup"><span data-stu-id="6c17d-153">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="6c17d-154">Depurar deadlock</span><span class="sxs-lookup"><span data-stu-id="6c17d-154">Debug deadlock</span></span>

<span data-ttu-id="6c17d-155">[Tutorial: debug deadlock](debug-deadlock.md) mostra como usar a ferramenta [dotnet-dump](dotnet-dump.md) para investigar threads e bloqueios.</span><span class="sxs-lookup"><span data-stu-id="6c17d-155">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>

### <a name="measure-performance-using-eventcounters"></a><span data-ttu-id="6c17d-156">Medir o desempenho usando o EventCounters</span><span class="sxs-lookup"><span data-stu-id="6c17d-156">Measure performance using EventCounters</span></span>

<span data-ttu-id="6c17d-157">[Tutorial: medir o desempenho usando o EventCounters no .net](event-counter-perf.md) mostra como usar a <xref:System.Diagnostics.Tracing.EventCounter> API para medir o desempenho em seu aplicativo .net.</span><span class="sxs-lookup"><span data-stu-id="6c17d-157">[Tutorial: Measure performance using EventCounters in .NET](event-counter-perf.md) shows you how to use the <xref:System.Diagnostics.Tracing.EventCounter> API to measure performance in your .NET app.</span></span>
