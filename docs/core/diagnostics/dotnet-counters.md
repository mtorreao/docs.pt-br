---
title: dotnet – ferramenta de diagnóstico de contadores – CLI do .NET
description: Saiba como instalar e usar a ferramenta dotnet-Counter CLI para monitoramento de integridade ad hoc e investigação de desempenho de primeiro nível.
ms.date: 11/17/2020
ms.openlocfilehash: 89695c77e7913d41f030890be7cc00947e42fa3a
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856049"
---
# <a name="investigate-performance-counters-dotnet-counters"></a><span data-ttu-id="4578f-103">Investigar contadores de desempenho (dotNet-contadores)</span><span class="sxs-lookup"><span data-stu-id="4578f-103">Investigate performance counters (dotnet-counters)</span></span>

<span data-ttu-id="4578f-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="4578f-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="4578f-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="4578f-105">Install</span></span>

<span data-ttu-id="4578f-106">Há duas maneiras de baixar e instalar `dotnet-counters` :</span><span class="sxs-lookup"><span data-stu-id="4578f-106">There are two ways to download and install `dotnet-counters`:</span></span>

- <span data-ttu-id="4578f-107">**ferramenta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="4578f-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="4578f-108">Para instalar a versão de lançamento mais recente do `dotnet-counters` [pacote NuGet](https://www.nuget.org/packages/dotnet-counters), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="4578f-108">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- <span data-ttu-id="4578f-109">**Download direto:**</span><span class="sxs-lookup"><span data-stu-id="4578f-109">**Direct download:**</span></span>

  <span data-ttu-id="4578f-110">Baixe o executável da ferramenta que corresponde à sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="4578f-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="4578f-111">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="4578f-111">OS</span></span>  | <span data-ttu-id="4578f-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="4578f-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="4578f-113">Windows</span><span class="sxs-lookup"><span data-stu-id="4578f-113">Windows</span></span> | <span data-ttu-id="4578f-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [ARM](https://aka.ms/dotnet-counters/win-arm) \| [ARM-x64](https://aka.ms/dotnet-counters/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="4578f-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span></span> |
  | <span data-ttu-id="4578f-115">macOS</span><span class="sxs-lookup"><span data-stu-id="4578f-115">macOS</span></span>   | [<span data-ttu-id="4578f-116">x64</span><span class="sxs-lookup"><span data-stu-id="4578f-116">x64</span></span>](https://aka.ms/dotnet-counters/osx-x64) |
  | <span data-ttu-id="4578f-117">Linux</span><span class="sxs-lookup"><span data-stu-id="4578f-117">Linux</span></span>   | <span data-ttu-id="4578f-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [ARM](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [MUSL-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [MUSL-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="4578f-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="4578f-119">Sinopse</span><span class="sxs-lookup"><span data-stu-id="4578f-119">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="4578f-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="4578f-120">Description</span></span>

<span data-ttu-id="4578f-121">`dotnet-counters` é uma ferramenta de monitoramento de desempenho para monitoramento de integridade ad hoc e investigação de desempenho de primeiro nível.</span><span class="sxs-lookup"><span data-stu-id="4578f-121">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="4578f-122">Ele pode observar os valores do contador de desempenho que são publicados por meio da <xref:System.Diagnostics.Tracing.EventCounter> API.</span><span class="sxs-lookup"><span data-stu-id="4578f-122">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="4578f-123">Por exemplo, você pode monitorar rapidamente coisas como o uso da CPU ou a taxa de exceções que estão sendo geradas em seu aplicativo .NET Core para ver se há algo suspeito antes de mergulhar em uma investigação de desempenho mais séria usando o `PerfView` ou o `dotnet-trace` .</span><span class="sxs-lookup"><span data-stu-id="4578f-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="4578f-124">Opções</span><span class="sxs-lookup"><span data-stu-id="4578f-124">Options</span></span>

- **`--version`**

  <span data-ttu-id="4578f-125">Exibe a versão do utilitário dotnet-Counters.</span><span class="sxs-lookup"><span data-stu-id="4578f-125">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4578f-126">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="4578f-126">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="4578f-127">Comandos</span><span class="sxs-lookup"><span data-stu-id="4578f-127">Commands</span></span>

| <span data-ttu-id="4578f-128">Comando</span><span class="sxs-lookup"><span data-stu-id="4578f-128">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="4578f-129">dotnet – coleta de contadores</span><span class="sxs-lookup"><span data-stu-id="4578f-129">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="4578f-130">dotnet – lista de contadores</span><span class="sxs-lookup"><span data-stu-id="4578f-130">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="4578f-131">dotnet – monitor de contadores</span><span class="sxs-lookup"><span data-stu-id="4578f-131">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="4578f-132">dotnet-contadores PS</span><span class="sxs-lookup"><span data-stu-id="4578f-132">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="4578f-133">dotnet – coleta de contadores</span><span class="sxs-lookup"><span data-stu-id="4578f-133">dotnet-counters collect</span></span>

<span data-ttu-id="4578f-134">Coletar periodicamente os valores de contador selecionados e exportá-los para um formato de arquivo especificado para o pós-processamento.</span><span class="sxs-lookup"><span data-stu-id="4578f-134">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="4578f-135">Sinopse</span><span class="sxs-lookup"><span data-stu-id="4578f-135">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="4578f-136">Opções</span><span class="sxs-lookup"><span data-stu-id="4578f-136">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="4578f-137">A ID do processo do qual coletar dados do contador.</span><span class="sxs-lookup"><span data-stu-id="4578f-137">The ID of the process to be collect counter data from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="4578f-138">O nome do processo do qual coletar dados do contador.</span><span class="sxs-lookup"><span data-stu-id="4578f-138">The name of the process to be collect counter data from.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="4578f-139">O nome da porta de diagnóstico a ser criada.</span><span class="sxs-lookup"><span data-stu-id="4578f-139">The name of the diagnostic port to create.</span></span> <span data-ttu-id="4578f-140">Consulte [usando a porta de diagnóstico](#using-diagnostic-port) para saber como usar essa opção para iniciar o monitoramento de contadores da inicialização do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4578f-140">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="4578f-141">O número de segundos de atraso entre a atualização dos contadores exibidos</span><span class="sxs-lookup"><span data-stu-id="4578f-141">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="4578f-142">Uma lista separada por vírgulas de contadores.</span><span class="sxs-lookup"><span data-stu-id="4578f-142">A comma-separated list of counters.</span></span> <span data-ttu-id="4578f-143">Os contadores podem ser especificados `provider_name[:counter_name]` .</span><span class="sxs-lookup"><span data-stu-id="4578f-143">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="4578f-144">Se o `provider_name` for usado sem uma lista de contadores de qualificação, todos os contadores do provedor serão mostrados.</span><span class="sxs-lookup"><span data-stu-id="4578f-144">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="4578f-145">Para descobrir os nomes de provedor e contador, use o comando [dotnet-Counters List](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="4578f-145">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="4578f-146">O formato a ser exportado.</span><span class="sxs-lookup"><span data-stu-id="4578f-146">The format to be exported.</span></span> <span data-ttu-id="4578f-147">Atualmente disponível: CSV, JSON.</span><span class="sxs-lookup"><span data-stu-id="4578f-147">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="4578f-148">O nome do arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="4578f-148">The name of the output file.</span></span>

- <span data-ttu-id="4578f-149">**`-- <command>` (para aplicativos de destino que executam o .NET 5,0 ou posterior somente)**</span><span class="sxs-lookup"><span data-stu-id="4578f-149">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="4578f-150">Após os parâmetros de configuração da coleção, o usuário pode acrescentar `--` seguido por um comando para iniciar um aplicativo .NET com pelo menos um tempo de execução de 5,0.</span><span class="sxs-lookup"><span data-stu-id="4578f-150">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="4578f-151">`dotnet-counters` o iniciará um processo com o comando fornecido e coletará as métricas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="4578f-151">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="4578f-152">Isso geralmente é útil para coletar métricas para o caminho de inicialização do aplicativo e pode ser usado para diagnosticar ou monitorar problemas que ocorrem antes ou logo após o ponto de entrada principal.</span><span class="sxs-lookup"><span data-stu-id="4578f-152">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4578f-153">O uso dessa opção monitora o primeiro processo do .NET 5,0 que se comunica de volta à ferramenta, o que significa que, se o comando iniciar vários aplicativos .NET, ele só coletará o primeiro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4578f-153">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="4578f-154">Portanto, é recomendável usar essa opção em aplicativos independentes ou usando a `dotnet exec <app.dll>` opção.</span><span class="sxs-lookup"><span data-stu-id="4578f-154">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4578f-155">Iniciar um executável .NET por meio de dotnet-Counters fará com que sua entrada/saída seja redirecionada e você não poderá interagir com seu STDIN/STDOUT.</span><span class="sxs-lookup"><span data-stu-id="4578f-155">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="4578f-156">Sair da ferramenta por meio de CTRL + C ou SIGTERM irá encerrar com segurança a ferramenta e o processo filho.</span><span class="sxs-lookup"><span data-stu-id="4578f-156">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="4578f-157">Se o processo filho for encerrado antes da ferramenta, a ferramenta também será encerrada e o rastreamento deverá ser visível com segurança.</span><span class="sxs-lookup"><span data-stu-id="4578f-157">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span> <span data-ttu-id="4578f-158">Se você precisar usar stdin/stdout, poderá usar a `--diagnostic-port` opção.</span><span class="sxs-lookup"><span data-stu-id="4578f-158">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="4578f-159">Consulte [usando a porta de diagnóstico](#using-diagnostic-port) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4578f-159">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

### <a name="examples"></a><span data-ttu-id="4578f-160">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4578f-160">Examples</span></span>

- <span data-ttu-id="4578f-161">Colete todos os contadores em um intervalo de atualização de 3 segundos e gere um CSV como saída:</span><span class="sxs-lookup"><span data-stu-id="4578f-161">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="4578f-162">Inicie `dotnet mvc.dll` o como um processo filho e comece a coletar contadores de tempo de execução e ASP.NET Core contadores de hospedagem da inicialização e salve-os como uma saída JSON:</span><span class="sxs-lookup"><span data-stu-id="4578f-162">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="4578f-163">dotnet – lista de contadores</span><span class="sxs-lookup"><span data-stu-id="4578f-163">dotnet-counters list</span></span>

<span data-ttu-id="4578f-164">Exibe uma lista de nomes e descrições de contadores, agrupados por provedor.</span><span class="sxs-lookup"><span data-stu-id="4578f-164">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="4578f-165">Sinopse</span><span class="sxs-lookup"><span data-stu-id="4578f-165">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="4578f-166">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4578f-166">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs per interval
    gen-1-gc-count                               Number of Gen 1 GCs per interval
    gen-2-gc-count                               Number of Gen 2 GCs per interval
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions per interval
    threadpool-thread-count                      Number of ThreadPool Threads
    monitor-lock-contention-count                Monitor Lock Contention Count
    threadpool-queue-length                      ThreadPool Work Items Queue Length
    threadpool-completed-items-count             ThreadPool Completed Work Items Count
    active-timer-count                           Active Timers Count

Microsoft.AspNetCore.Hosting
    requests-per-second                  Request rate
    total-requests                       Total number of requests
    current-requests                     Current number of requests
    failed-requests                      Failed number of requests
```

> [!NOTE]
> <span data-ttu-id="4578f-167">Os `Microsoft.AspNetCore.Hosting` contadores são exibidos quando há processos identificados que dão suporte a esses contadores, por exemplo, quando um aplicativo ASP.NET Core está em execução no computador host.</span><span class="sxs-lookup"><span data-stu-id="4578f-167">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="4578f-168">dotnet – monitor de contadores</span><span class="sxs-lookup"><span data-stu-id="4578f-168">dotnet-counters monitor</span></span>

<span data-ttu-id="4578f-169">Exibe a atualização periódica de valores dos contadores selecionados.</span><span class="sxs-lookup"><span data-stu-id="4578f-169">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="4578f-170">Sinopse</span><span class="sxs-lookup"><span data-stu-id="4578f-170">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="4578f-171">Opções</span><span class="sxs-lookup"><span data-stu-id="4578f-171">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="4578f-172">A ID do processo a ser monitorado.</span><span class="sxs-lookup"><span data-stu-id="4578f-172">The ID of the process to be monitored.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="4578f-173">O nome do processo a ser monitorado.</span><span class="sxs-lookup"><span data-stu-id="4578f-173">The name of the process to be monitored.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="4578f-174">O nome da porta de diagnóstico a ser criada.</span><span class="sxs-lookup"><span data-stu-id="4578f-174">The name of the diagnostic port to create.</span></span> <span data-ttu-id="4578f-175">Consulte [usando a porta de diagnóstico](#using-diagnostic-port) para saber como usar essa opção para iniciar o monitoramento de contadores da inicialização do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4578f-175">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="4578f-176">O número de segundos de atraso entre a atualização dos contadores exibidos</span><span class="sxs-lookup"><span data-stu-id="4578f-176">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="4578f-177">Uma lista separada por vírgulas de contadores.</span><span class="sxs-lookup"><span data-stu-id="4578f-177">A comma-separated list of counters.</span></span> <span data-ttu-id="4578f-178">Os contadores podem ser especificados `provider_name[:counter_name]` .</span><span class="sxs-lookup"><span data-stu-id="4578f-178">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="4578f-179">Se o `provider_name` for usado sem uma lista de contadores de qualificação, todos os contadores do provedor serão mostrados.</span><span class="sxs-lookup"><span data-stu-id="4578f-179">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="4578f-180">Para descobrir os nomes de provedor e contador, use o comando [dotnet-Counters List](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="4578f-180">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="4578f-181">**`-- <command>` (para aplicativos de destino que executam o .NET 5,0 ou posterior somente)**</span><span class="sxs-lookup"><span data-stu-id="4578f-181">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="4578f-182">Após os parâmetros de configuração da coleção, o usuário pode acrescentar `--` seguido por um comando para iniciar um aplicativo .NET com pelo menos um tempo de execução de 5,0.</span><span class="sxs-lookup"><span data-stu-id="4578f-182">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="4578f-183">`dotnet-counters` o iniciará um processo com o comando fornecido e monitorará as métricas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="4578f-183">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="4578f-184">Isso geralmente é útil para coletar métricas para o caminho de inicialização do aplicativo e pode ser usado para diagnosticar ou monitorar problemas que ocorrem antes ou logo após o ponto de entrada principal.</span><span class="sxs-lookup"><span data-stu-id="4578f-184">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4578f-185">O uso dessa opção monitora o primeiro processo do .NET 5,0 que se comunica de volta à ferramenta, o que significa que, se o comando iniciar vários aplicativos .NET, ele só coletará o primeiro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4578f-185">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="4578f-186">Portanto, é recomendável usar essa opção em aplicativos independentes ou usando a `dotnet exec <app.dll>` opção.</span><span class="sxs-lookup"><span data-stu-id="4578f-186">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4578f-187">Iniciar um executável .NET por meio de dotnet-Counters fará com que sua entrada/saída seja redirecionada e você não poderá interagir com seu STDIN/STDOUT.</span><span class="sxs-lookup"><span data-stu-id="4578f-187">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="4578f-188">Sair da ferramenta por meio de CTRL + C ou SIGTERM irá encerrar com segurança a ferramenta e o processo filho.</span><span class="sxs-lookup"><span data-stu-id="4578f-188">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="4578f-189">Se o processo filho for encerrado antes da ferramenta, a ferramenta também será encerrada e o rastreamento deverá ser visível com segurança.</span><span class="sxs-lookup"><span data-stu-id="4578f-189">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span> <span data-ttu-id="4578f-190">Se você precisar usar stdin/stdout, poderá usar a `--diagnostic-port` opção.</span><span class="sxs-lookup"><span data-stu-id="4578f-190">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="4578f-191">Consulte [usando a porta de diagnóstico](#using-diagnostic-port) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4578f-191">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

### <a name="examples"></a><span data-ttu-id="4578f-192">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4578f-192">Examples</span></span>

- <span data-ttu-id="4578f-193">Monitorar todos os contadores de `System.Runtime` em um intervalo de atualização de 3 segundos:</span><span class="sxs-lookup"><span data-stu-id="4578f-193">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 --counters System.Runtime
  Press p to pause, r to resume, q to quit.
      Status: Running

  [System.Runtime]
      % Time in GC since last GC (%)                                 0
      Allocation Rate (B / 1 sec)                                5,376
      CPU Usage (%)                                                  0
      Exception Count (Count / 1 sec)                                0
      GC Fragmentation (%)                                          48.467
      GC Heap Size (MB)                                              0
      Gen 0 GC Count (Count / 1 sec)                                 1
      Gen 0 Size (B)                                                24
      Gen 1 GC Count (Count / 1 sec)                                 1
      Gen 1 Size (B)                                                24
      Gen 2 GC Count (Count / 1 sec)                                 1
      Gen 2 Size (B)                                           272,000
      IL Bytes Jitted (B)                                       19,449
      LOH Size (B)                                              19,640
      Monitor Lock Contention Count (Count / 1 sec)                  0
      Number of Active Timers                                        0
      Number of Assemblies Loaded                                    7
      Number of Methods Jitted                                     166
      POH (Pinned Object Heap) Size (B)                             24
      ThreadPool Completed Work Item Count (Count / 1 sec)           0
      ThreadPool Queue Length                                        0
      ThreadPool Thread Count                                        2
      Working Set (MB)                                              19
  ```

- <span data-ttu-id="4578f-194">Monitorar apenas o uso da CPU e o tamanho do heap do GC de `System.Runtime` :</span><span class="sxs-lookup"><span data-stu-id="4578f-194">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="4578f-195">Monitorar `EventCounter` valores de definidos pelo usuário `EventSource` .</span><span class="sxs-lookup"><span data-stu-id="4578f-195">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="4578f-196">Para obter mais informações, consulte [tutorial: medir o desempenho usando o EventCounters no .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="4578f-196">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="4578f-197">Exiba todos os contadores conhecidos que estão disponíveis no `dotnet-counters` :</span><span class="sxs-lookup"><span data-stu-id="4578f-197">View all well-known counters that are available in `dotnet-counters`:</span></span>

  ```console
  > dotnet-counters list

  Showing well-known counters for .NET (Core) version 3.1 only. Specific processes may support additional counters.
  System.Runtime              
      cpu-usage                          The percent of process' CPU usage relative to all of the system CPU resources [0-100]
      working-set                        Amount of working set used by the process (MB)
      gc-heap-size                       Total heap size reported by the GC (MB)
      gen-0-gc-count                     Number of Gen 0 GCs between update intervals
      gen-1-gc-count                     Number of Gen 1 GCs between update intervals
      gen-2-gc-count                     Number of Gen 2 GCs between update intervals
      time-in-gc                         % time in GC since the last GC
      gen-0-size                         Gen 0 Heap Size
      gen-1-size                         Gen 1 Heap Size
      gen-2-size                         Gen 2 Heap Size
      loh-size                           LOH Size
      alloc-rate                         Number of bytes allocated in the managed heap between update intervals
      assembly-count                     Number of Assemblies Loaded
      exception-count                    Number of Exceptions / sec
      threadpool-thread-count            Number of ThreadPool Threads
      monitor-lock-contention-count      Number of times there were contention when trying to take the monitor lock between update intervals
      threadpool-queue-length            ThreadPool Work Items Queue Length
      threadpool-completed-items-count   ThreadPool Completed Work Items Count
      active-timer-count                 Number of timers that are currently active

  Microsoft.AspNetCore.Hosting
      requests-per-second                Number of requests between update intervals
      total-requests                     Total number of requests
      current-requests                   Current number of requests
      failed-requests                    Failed number of requests
  ```

- <span data-ttu-id="4578f-198">Exiba todos os contadores conhecidos que estão disponíveis no `dotnet-counters` para aplicativos .NET 5:</span><span class="sxs-lookup"><span data-stu-id="4578f-198">View all well-known counters that are available in `dotnet-counters` for .NET 5 apps:</span></span>

  ```console
  > dotnet-counters list --runtime-version 5.0

  Showing well-known counters for .NET (Core) version 5.0 only. Specific processes may support additional counters.
  System.Runtime                     
      cpu-usage                          The percent of process' CPU usage relative to all of the system CPU resources [0-100]
      working-set                        Amount of working set used by the process (MB)
      gc-heap-size                       Total heap size reported by the GC (MB)
      gen-0-gc-count                     Number of Gen 0 GCs between update intervals
      gen-1-gc-count                     Number of Gen 1 GCs between update intervals
      gen-2-gc-count                     Number of Gen 2 GCs between update intervals
      time-in-gc                         % time in GC since the last GC
      gen-0-size                         Gen 0 Heap Size
      gen-1-size                         Gen 1 Heap Size
      gen-2-size                         Gen 2 Heap Size
      loh-size                           LOH Size
      poh-size                           POH (Pinned Object Heap) Size
      alloc-rate                         Number of bytes allocated in the managed heap between update intervals
      gc-fragmentation                   GC Heap Fragmentation
      assembly-count                     Number of Assemblies Loaded
      exception-count                    Number of Exceptions / sec
      threadpool-thread-count            Number of ThreadPool Threads
      monitor-lock-contention-count      Number of times there were contention when trying to take the monitor lock between update intervals
      threadpool-queue-length            ThreadPool Work Items Queue Length
      threadpool-completed-items-count   ThreadPool Completed Work Items Count
      active-timer-count                 Number of timers that are currently active
      il-bytes-jitted                    Total IL bytes jitted
      methods-jitted-count               Number of methods jitted

  Microsoft.AspNetCore.Hosting       
      requests-per-second   Number of requests between update intervals
      total-requests        Total number of requests
      current-requests      Current number of requests
      failed-requests       Failed number of requests

  Microsoft-AspNetCore-Server-Kestrel
      connections-per-second      Number of connections between update intervals
      total-connections           Total Connections
      tls-handshakes-per-second   Number of TLS Handshakes made between update intervals
      total-tls-handshakes        Total number of TLS handshakes made
      current-tls-handshakes      Number of currently active TLS handshakes
      failed-tls-handshakes       Total number of failed TLS handshakes
      current-connections         Number of current connections
      connection-queue-length     Length of Kestrel Connection Queue
      request-queue-length        Length total HTTP request queue

  System.Net.Http                    
      requests-started        Total Requests Started
      requests-started-rate   Number of Requests Started between update intervals
      requests-aborted        Total Requests Aborted
      requests-aborted-rate   Number of Requests Aborted between update intervals
      current-requests        Current Requests
  ```

- <span data-ttu-id="4578f-199">Inicie `my-aspnet-server.exe` e monitore o número de assemblies carregados a partir de sua inicialização (somente .net 5,0 ou posterior):</span><span class="sxs-lookup"><span data-stu-id="4578f-199">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4578f-200">Isso funciona somente para aplicativos que executam o .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4578f-200">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="4578f-201">Inicie `my-aspnet-server.exe` com `arg1` e `arg2` como argumentos de linha de comando e monitore seu conjunto de trabalho e o tamanho do heap de GC de sua inicialização (somente .NET 5,0 ou posterior):</span><span class="sxs-lookup"><span data-stu-id="4578f-201">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4578f-202">Isso funciona somente para aplicativos que executam o .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4578f-202">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[working-set,gc-heap-size] -- my-aspnet-server.exe arg1 arg2
  ```

  ```console
  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      GC Heap Size (MB)                                 39
      Working Set (MB)                                  59
  ```

## <a name="dotnet-counters-ps"></a><span data-ttu-id="4578f-203">dotnet-contadores PS</span><span class="sxs-lookup"><span data-stu-id="4578f-203">dotnet-counters ps</span></span>

<span data-ttu-id="4578f-204">Exibe uma lista de processos dotnet que podem ser monitorados.</span><span class="sxs-lookup"><span data-stu-id="4578f-204">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="4578f-205">Sinopse</span><span class="sxs-lookup"><span data-stu-id="4578f-205">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="4578f-206">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4578f-206">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/user/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```

## <a name="using-diagnostic-port"></a><span data-ttu-id="4578f-207">Usando a porta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4578f-207">Using diagnostic port</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="4578f-208">Isso funciona somente para aplicativos que executam o .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4578f-208">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="4578f-209">A porta de diagnóstico é um novo recurso de tempo de execução que foi adicionado no .NET 5 que permite que você inicie o monitoramento ou coleta de contadores da inicialização do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4578f-209">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start monitoring or collecting counters from app startup.</span></span> <span data-ttu-id="4578f-210">Para fazer isso usando o `dotnet-counters` , você pode usar o `dotnet-counters <collect|monitor> -- <command>` conforme descrito nos exemplos acima ou usar a `--diagnostic-port` opção.</span><span class="sxs-lookup"><span data-stu-id="4578f-210">To do this using `dotnet-counters`, you can either use `dotnet-counters <collect|monitor> -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="4578f-211">Usar `dotnet-counters <collect|monitor> -- <command>` o para iniciar o aplicativo como um processo filho é a maneira mais simples de monitorá-lo rapidamente a partir de sua inicialização.</span><span class="sxs-lookup"><span data-stu-id="4578f-211">Using `dotnet-counters <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly monitor it from its startup.</span></span>

<span data-ttu-id="4578f-212">No entanto, quando você quiser obter um controle mais preciso sobre o tempo de vida do aplicativo que está sendo monitorado (por exemplo, monitorar o aplicativo pelos primeiros 10 minutos e continuar executando) ou se precisar interagir com o aplicativo usando a CLI, o uso da `--diagnostic-port` opção permitirá que você controle o aplicativo de destino que está sendo monitorado e `dotnet-counters` .</span><span class="sxs-lookup"><span data-stu-id="4578f-212">However, when you want to gain a finer control over the lifetime of the app being monitored (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-counters`.</span></span>

1. <span data-ttu-id="4578f-213">O comando a seguir faz o dotnet-Counters criar um soquete de diagnóstico chamado `myport.sock` e aguardar uma conexão.</span><span class="sxs-lookup"><span data-stu-id="4578f-213">The command below makes dotnet-counters create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-counters collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="4578f-214">Saída:</span><span class="sxs-lookup"><span data-stu-id="4578f-214">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="4578f-215">Em um console separado, inicie o aplicativo de destino com a variável de ambiente `DOTNET_DiagnosticPorts` definida como o valor na `dotnet-counters` saída.</span><span class="sxs-lookup"><span data-stu-id="4578f-215">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-counters` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="4578f-216">Isso deve, então, habilitar `dotnet-counters` para começar a coletar contadores em `my-dotnet-app` :</span><span class="sxs-lookup"><span data-stu-id="4578f-216">This should then enable `dotnet-counters` to start collecting counters on `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="4578f-217">Iniciar seu aplicativo com `dotnet run` pode ser problemático porque a CLI dotnet pode gerar muitos processos filho que não são seu aplicativo e podem se conectar `dotnet-counters` antes do seu aplicativo, deixando seu aplicativo para ser suspenso em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="4578f-217">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-counters` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="4578f-218">É recomendável que você use diretamente uma versão independente do aplicativo ou use `dotnet exec` para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4578f-218">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>
