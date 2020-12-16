---
title: Rastreando aplicativos .NET com PerfCollect.
description: Um tutorial que orienta você pela coleta de um rastreamento com perfcollect no .NET.
ms.topic: tutorial
ms.date: 10/23/2020
ms.openlocfilehash: 53e4584953d2af4e766daadfa757cca752ae7329
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593214"
---
# <a name="trace-net-applications-with-perfcollect"></a><span data-ttu-id="46e52-103">Rastrear aplicativos .NET com PerfCollect</span><span class="sxs-lookup"><span data-stu-id="46e52-103">Trace .NET applications with PerfCollect</span></span>

<span data-ttu-id="46e52-104">**Este artigo aplica-se a: ✔️** SDK do .net Core 2,1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="46e52-104">**This article applies to: ✔️** .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="46e52-105">Quando são encontrados problemas de desempenho no Linux, a coleta de um rastreamento com `perfcollect` o pode ser usada para reunir informações detalhadas sobre o que estava acontecendo no computador no momento do problema de desempenho.</span><span class="sxs-lookup"><span data-stu-id="46e52-105">When performance problems are encountered on Linux, collecting a trace with `perfcollect` can be used to gather detailed information about what was happening on the machine at the time of the performance problem.</span></span>

<span data-ttu-id="46e52-106">`perfcollect` é um script bash que aproveita a [geração de Tookit-Next de rastreamento do Linux (LTTng)](https://lttng.org) para coletar eventos gravados do tempo de execução ou de qualquer [EventSource](xref:System.Diagnostics.Tracing.EventListener), bem como [perf](https://perf.wiki.kernel.org/) , para coletar amostras de CPU do processo de destino.</span><span class="sxs-lookup"><span data-stu-id="46e52-106">`perfcollect` is a bash script that leverages [Linux Tracing Tookit-Next Generation (LTTng)](https://lttng.org) to collect events written from the runtime or any [EventSource](xref:System.Diagnostics.Tracing.EventListener), as well as [perf](https://perf.wiki.kernel.org/) to collect CPU samples of the target process.</span></span>

## <a name="prepare-your-machine"></a><span data-ttu-id="46e52-107">Preparar seu computador</span><span class="sxs-lookup"><span data-stu-id="46e52-107">Prepare your machine</span></span>

<span data-ttu-id="46e52-108">Siga estas etapas para preparar seu computador para coletar um rastreamento de desempenho com o `perfcollect` .</span><span class="sxs-lookup"><span data-stu-id="46e52-108">Follow these steps to prepare your machine to collect a performance trace with `perfcollect`.</span></span>

> [!NOTE]
> <span data-ttu-id="46e52-109">Se você estiver em um ambiente de contêiner, seu contêiner precisará ter `SYS_ADMIN` capacidade.</span><span class="sxs-lookup"><span data-stu-id="46e52-109">If you are in a container environment, your container needs to have `SYS_ADMIN` capability.</span></span> <span data-ttu-id="46e52-110">Para obter mais informações sobre como rastrear aplicativos dentro de contêineres usando o PerfCollect, consulte [coletar diagnósticos em contêineres](./diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="46e52-110">For more information on tracing applications inside containers using PerfCollect, see [Collect diagnostics in containers](./diagnostics-in-containers.md).</span></span>

1. <span data-ttu-id="46e52-111">Baixar `perfcollect` .</span><span class="sxs-lookup"><span data-stu-id="46e52-111">Download `perfcollect`.</span></span>

    > ```bash
    > curl -OL https://aka.ms/perfcollect
    > ```

2. <span data-ttu-id="46e52-112">Torne o script executável.</span><span class="sxs-lookup"><span data-stu-id="46e52-112">Make the script executable.</span></span>

    > ```bash
    > chmod +x perfcollect
    > ```

3. <span data-ttu-id="46e52-113">Instalar os pré-requisitos de rastreamento-essas são as bibliotecas de rastreamento reais.</span><span class="sxs-lookup"><span data-stu-id="46e52-113">Install tracing prerequisites - these are the actual tracing libraries.</span></span>

    > ```bash
    > sudo ./perfcollect install
    > ```

    <span data-ttu-id="46e52-114">Isso instalará os seguintes pré-requisitos em seu computador:</span><span class="sxs-lookup"><span data-stu-id="46e52-114">This will install the following prerequisites on your machine:</span></span>

    1. <span data-ttu-id="46e52-115">`perf`: o subsistema de eventos de desempenho do Linux e o aplicativo de coleta/Visualizador do modo de usuário complementar.</span><span class="sxs-lookup"><span data-stu-id="46e52-115">`perf`: the Linux Performance Events subsystem and companion user-mode collection/viewer application.</span></span> <span data-ttu-id="46e52-116">`perf` faz parte da origem do kernel do Linux, mas geralmente não é instalado por padrão.</span><span class="sxs-lookup"><span data-stu-id="46e52-116">`perf` is part of the Linux kernel source, but is not usually installed by default.</span></span>

    2. <span data-ttu-id="46e52-117">`LTTng`: Usado para capturar dados de eventos emitidos em tempo de execução pelo CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="46e52-117">`LTTng`: Used to capture event data emitted at runtime by CoreCLR.</span></span> <span data-ttu-id="46e52-118">Esses dados são usados para analisar o comportamento de vários componentes de tempo de execução, como GC, JIT e pool de threads.</span><span class="sxs-lookup"><span data-stu-id="46e52-118">This data is then used to analyze the behavior of various runtime components such as the GC, JIT, and thread pool.</span></span>

<span data-ttu-id="46e52-119">As versões recentes do .NET Core e da ferramenta de desempenho do Linux dão suporte à resolução automática de nomes de método para código de estrutura.</span><span class="sxs-lookup"><span data-stu-id="46e52-119">Recent versions of .NET Core and the Linux perf tool support automatic resolution of method names for framework code.</span></span> <span data-ttu-id="46e52-120">Se você estiver trabalhando com o .NET Core versão 3,1 ou menos, será necessária uma etapa extra.</span><span class="sxs-lookup"><span data-stu-id="46e52-120">If you are working with .NET Core version 3.1 or less, an extra step is necessary.</span></span> <span data-ttu-id="46e52-121">Consulte [resolvendo símbolos de estrutura](#resolve-framework-symbols) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="46e52-121">See [Resolving Framework Symbols](#resolve-framework-symbols) for details.</span></span>

<span data-ttu-id="46e52-122">Para resolver nomes de método de DLLs de tempo de execução nativas (como libcoreclr.so), o `perfcollect` resolve os símbolos para eles ao converter os dados, mas somente se os símbolos desses binários estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="46e52-122">For resolving method names of native runtime DLLs (such as libcoreclr.so), `perfcollect` will resolve symbols for them when it converts the data, but only if the symbols for these binaries are present.</span></span> <span data-ttu-id="46e52-123">Consulte [obtendo símbolos para a seção de tempo de execução nativo](#get-symbols-for-the-native-runtime) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="46e52-123">See [Getting Symbols for the Native Runtime](#get-symbols-for-the-native-runtime) section for details.</span></span>

## <a name="collect-a-trace"></a><span data-ttu-id="46e52-124">Coletar um rastreamento</span><span class="sxs-lookup"><span data-stu-id="46e52-124">Collect a trace</span></span>

1. <span data-ttu-id="46e52-125">Ter dois shells disponíveis-um para controlar o rastreamento, conhecido como **[Trace]** e outro para executar o aplicativo, chamado de **[App]**.</span><span class="sxs-lookup"><span data-stu-id="46e52-125">Have two shells available - one for controlling tracing, referred to as **[Trace]**, and one for running the application, referred to as **[App]**.</span></span>

2. <span data-ttu-id="46e52-126">**[Rastreamento]** Iniciar coleção.</span><span class="sxs-lookup"><span data-stu-id="46e52-126">**[Trace]** Start collection.</span></span>

    > ```bash
    > sudo ./perfcollect collect sampleTrace
    > ```

    <span data-ttu-id="46e52-127">Saída esperada:</span><span class="sxs-lookup"><span data-stu-id="46e52-127">Expected Output:</span></span>

    > ```bash
    > Collection started.  Press CTRL+C to stop.
    > ```

3. <span data-ttu-id="46e52-128">**[Aplicativo]** Configure o Shell de aplicativo com as seguintes variáveis de ambiente – isso habilita a configuração de rastreamento do CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="46e52-128">**[App]** Set up the application shell with the following environment variables - this enables tracing configuration of CoreCLR.</span></span>

    > ```bash
    > export COMPlus_PerfMapEnabled=1
    > export COMPlus_EnableEventLog=1
    > ```

4. <span data-ttu-id="46e52-129">**[Aplicativo]** Execute o aplicativo-deixe que ele seja executado desde que você precise para capturar o problema de desempenho.</span><span class="sxs-lookup"><span data-stu-id="46e52-129">**[App]** Run the app - let it run as long as you need to in order to capture the performance problem.</span></span> <span data-ttu-id="46e52-130">O comprimento exato pode ser tão curto quanto necessário, desde que ele Capture suficientemente a janela de tempo onde o problema de desempenho que você deseja investigar ocorre.</span><span class="sxs-lookup"><span data-stu-id="46e52-130">The exact length can be as short as you need as long as it sufficiently captures the window of time where the performance problem you want to investigate occurs.</span></span>

    > ```bash
    > dotnet run
    > ```

5. <span data-ttu-id="46e52-131">**[Rastreamento]** Parar coleção-pressione CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="46e52-131">**[Trace]** Stop collection - hit CTRL+C.</span></span>

    > ```bash
    > ^C
    > ...STOPPED.
    >
    > Starting post-processing. This may take some time.
    >
    > Generating native image symbol files
    > ...SKIPPED
    > Saving native symbols
    > ...FINISHED
    > Exporting perf.data file
    > ...FINISHED
    > Compressing trace files
    > ...FINISHED
    > Cleaning up artifacts
    > ...FINISHED
    >
    > Trace saved to sampleTrace.trace.zip
    > ```

    <span data-ttu-id="46e52-132">O arquivo de rastreamento compactado agora é armazenado no diretório de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="46e52-132">The compressed trace file is now stored in the current working directory.</span></span>

## <a name="view-a-trace"></a><span data-ttu-id="46e52-133">Exibir um rastreamento</span><span class="sxs-lookup"><span data-stu-id="46e52-133">View a trace</span></span>

<span data-ttu-id="46e52-134">Há várias opções para exibir o rastreamento que foi coletado.</span><span class="sxs-lookup"><span data-stu-id="46e52-134">There are a number of options for viewing the trace that was collected.</span></span> <span data-ttu-id="46e52-135">Os rastreamentos são mais bem exibidos usando o [Perfview](https://aka.ms/perfview) no Windows, mas eles podem ser exibidos diretamente no Linux usando- `PerfCollect` se ou `TraceCompass` .</span><span class="sxs-lookup"><span data-stu-id="46e52-135">Traces are best viewed using [PerfView](https://aka.ms/perfview) on Windows, but they can be viewed directly on Linux using `PerfCollect` itself or `TraceCompass`.</span></span>

### <a name="use-perfcollect-to-view-the-trace-file"></a><span data-ttu-id="46e52-136">Use PerfCollect para exibir o arquivo de rastreamento</span><span class="sxs-lookup"><span data-stu-id="46e52-136">Use PerfCollect to view the trace file</span></span>

<span data-ttu-id="46e52-137">Você pode usar o perfcollect em si para exibir o rastreamento que você coletou.</span><span class="sxs-lookup"><span data-stu-id="46e52-137">You can use perfcollect itself to view the trace that you collected.</span></span> <span data-ttu-id="46e52-138">Para isso, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="46e52-138">To do this, use the following command:</span></span>

```bash
./perfcollect view sampleTrace.trace.zip
```

<span data-ttu-id="46e52-139">Por padrão, isso mostrará o rastreamento de CPU do aplicativo usando `perf` .</span><span class="sxs-lookup"><span data-stu-id="46e52-139">By default, this will show the CPU trace of the application using `perf`.</span></span>

<span data-ttu-id="46e52-140">Para examinar os eventos que foram coletados por meio `LTTng` do, você pode passar o sinalizador `-viewer lttng` para ver os eventos individuais:</span><span class="sxs-lookup"><span data-stu-id="46e52-140">To look at the events that were collected via `LTTng`, you can pass in the flag `-viewer lttng` to see the individual events:</span></span>

```bash
./perfcollect view sampleTrace.trace.zip -viewer lttng
```

<span data-ttu-id="46e52-141">Isso usará `babeltrace` o visualizador para imprimir a carga de eventos:</span><span class="sxs-lookup"><span data-stu-id="46e52-141">This will use `babeltrace` viewer to print the events payload:</span></span>

```bash
# [01:02:18.189217659] (+0.020132603) ubuntu-xenial DotNETRuntime:ExceptionThrown_V1: { cpu_id = 0 }, { ExceptionType = "System.Exception", ExceptionMessage = "An exception happened", ExceptionEIP = 139875671834775, ExceptionHRESULT = 2148734208, ExceptionFlags = 16, ClrInstanceID = 0 }
# [01:02:18.189250227] (+0.020165171) ubuntu-xenial DotNETRuntime:ExceptionCatchStart: { cpu_id = 0 }, { EntryEIP = 139873639728404, MethodID = 139873626968120, MethodName = "void [helloworld] helloworld.Program::Main(string[])", ClrInstanceID = 0 }
```

### <a name="use-perfview-to-open-the-trace-file"></a><span data-ttu-id="46e52-142">Use PerfView para abrir o arquivo de rastreamento</span><span class="sxs-lookup"><span data-stu-id="46e52-142">Use PerfView to open the trace file</span></span>

<span data-ttu-id="46e52-143">Para ver uma exibição agregada do exemplo de CPU e dos eventos, você pode usar `PerfView` em um computador Windows.</span><span class="sxs-lookup"><span data-stu-id="46e52-143">To see an aggregate view of both the CPU sample and the events, you can use `PerfView` on a Windows machine.</span></span>

1. <span data-ttu-id="46e52-144">Copie o arquivo de trace.zip do Linux para um computador Windows.</span><span class="sxs-lookup"><span data-stu-id="46e52-144">Copy the trace.zip file from Linux to a Windows machine.</span></span>

2. <span data-ttu-id="46e52-145">Baixe o PerfView de <https://aka.ms/perfview> .</span><span class="sxs-lookup"><span data-stu-id="46e52-145">Download PerfView from <https://aka.ms/perfview>.</span></span>

3. <span data-ttu-id="46e52-146">Executar PerfView.exe</span><span class="sxs-lookup"><span data-stu-id="46e52-146">Run PerfView.exe</span></span>

    > ```cmd
    > PerfView.exe <path to trace.zip file>
    > ```

<span data-ttu-id="46e52-147">PerfView exibirá a lista de exibições com suporte com base nos dados contidos no arquivo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="46e52-147">PerfView will display the list of views that are supported based on the data contained in the trace file.</span></span>

- <span data-ttu-id="46e52-148">Para investigações de CPU, escolha **pilhas de CPU**.</span><span class="sxs-lookup"><span data-stu-id="46e52-148">For CPU investigations, choose **CPU stacks**.</span></span>

- <span data-ttu-id="46e52-149">Para obter informações detalhadas do GC, escolha **GCStats**.</span><span class="sxs-lookup"><span data-stu-id="46e52-149">For detailed GC information, choose **GCStats**.</span></span>

- <span data-ttu-id="46e52-150">Para obter informações de JIT por processo/módulo/método, escolha **JITStats**.</span><span class="sxs-lookup"><span data-stu-id="46e52-150">For per-process/module/method JIT information, choose **JITStats**.</span></span>

- <span data-ttu-id="46e52-151">Se não houver uma exibição para as informações necessárias, você poderá tentar procurar os eventos na exibição de eventos brutos.</span><span class="sxs-lookup"><span data-stu-id="46e52-151">If there is not a view for the information you need, you can try looking for the events in the raw events view.</span></span>  <span data-ttu-id="46e52-152">Escolha **eventos**.</span><span class="sxs-lookup"><span data-stu-id="46e52-152">Choose **Events**.</span></span>

<span data-ttu-id="46e52-153">Para obter mais informações sobre como interpretar exibições no PerfView, consulte links de ajuda na própria exibição ou na janela principal do PerfView, escolha **ajuda – >guia de usuários**.</span><span class="sxs-lookup"><span data-stu-id="46e52-153">For more information on how to interpret views in PerfView, see help links in the view itself, or from the main window in PerfView, choose **Help->Users Guide**.</span></span>

### <a name="use-tracecompass-to-open-the-trace-file"></a><span data-ttu-id="46e52-154">Use TraceCompass para abrir o arquivo de rastreamento</span><span class="sxs-lookup"><span data-stu-id="46e52-154">Use TraceCompass to open the trace file</span></span>

<span data-ttu-id="46e52-155">O [Eclipse TraceCompass](https://www.eclipse.org/tracecompass/) é outra opção que você pode usar para exibir os rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="46e52-155">[Eclipse TraceCompass](https://www.eclipse.org/tracecompass/) is another option you can use to view the traces.</span></span> <span data-ttu-id="46e52-156">`TraceCompass` também funciona em computadores Linux, portanto, você não precisa mover seu rastreamento para um computador Windows.</span><span class="sxs-lookup"><span data-stu-id="46e52-156">`TraceCompass` works on Linux machines as well, so you don't need to move your trace over to a Windows machine.</span></span> <span data-ttu-id="46e52-157">Para usar `TraceCompass` o para abrir o arquivo de rastreamento, será necessário descompactar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="46e52-157">To use `TraceCompass` to open your trace file, you will need to unzip the file.</span></span>

```bash
unzip myTrace.trace.zip
```

<span data-ttu-id="46e52-158">`perfcollect` o salvará o rastreamento LTTng coletado em um formato de arquivo CTF em um subdiretório no `lttngTrace` .</span><span class="sxs-lookup"><span data-stu-id="46e52-158">`perfcollect` will save the LTTng trace it collected into a CTF file format in a subdirectory in the `lttngTrace`.</span></span> <span data-ttu-id="46e52-159">Especificamente, o arquivo CTF estará localizado em um diretório parecido com `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\` .</span><span class="sxs-lookup"><span data-stu-id="46e52-159">Specifically, the CTF file will be located in a directory that looks like `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\`.</span></span>

<span data-ttu-id="46e52-160">Você pode abrir o arquivo de rastreamento CTF no selecionando `TraceCompass` `File -> Open Trace` e selecionando o `metadata` arquivo.</span><span class="sxs-lookup"><span data-stu-id="46e52-160">You can open the CTF trace file in `TraceCompass` by selecting `File -> Open Trace` and select the `metadata` file.</span></span>

<span data-ttu-id="46e52-161">Para obter mais detalhes, consulte a [ `TraceCompass` documentação](https://www.eclipse.org/tracecompass/).</span><span class="sxs-lookup"><span data-stu-id="46e52-161">For more details, please refer to [`TraceCompass` documentation](https://www.eclipse.org/tracecompass/).</span></span>

## <a name="resolve-framework-symbols"></a><span data-ttu-id="46e52-162">Resolver símbolos de estrutura</span><span class="sxs-lookup"><span data-stu-id="46e52-162">Resolve framework symbols</span></span>

<span data-ttu-id="46e52-163">Os símbolos de estrutura precisam ser gerados manualmente no momento em que o rastreamento é coletado.</span><span class="sxs-lookup"><span data-stu-id="46e52-163">Framework symbols need to be manually generated at the time the trace is collected.</span></span> <span data-ttu-id="46e52-164">Eles são diferentes dos símbolos de nível de aplicativo porque a estrutura é pré-compilado enquanto o código do aplicativo é compilado just-in-time.</span><span class="sxs-lookup"><span data-stu-id="46e52-164">They are different than app-level symbols because the framework is pre-compiled while app code is just-in-time-compiled.</span></span> <span data-ttu-id="46e52-165">Para o código de estrutura que foi pré-compilado ao código nativo, você precisa chamar `crossgen` isso que sabe como gerar o mapeamento do código nativo para o nome dos métodos.</span><span class="sxs-lookup"><span data-stu-id="46e52-165">For framework code that was precompiled to native code, you need to call `crossgen` that knows how to generate the mapping from the native code to the name of the methods.</span></span>

<span data-ttu-id="46e52-166">`perfcollect` pode lidar com a maioria dos detalhes para você, mas ele precisa ter `crossgen` disponível.</span><span class="sxs-lookup"><span data-stu-id="46e52-166">`perfcollect` can handle most of the details for you, but it needs to have `crossgen` available.</span></span> <span data-ttu-id="46e52-167">Por padrão, ele não é instalado com a distribuição do .NET.</span><span class="sxs-lookup"><span data-stu-id="46e52-167">By default it is not installed with .NET distribution.</span></span> <span data-ttu-id="46e52-168">Se `crossgen` não estiver, o `perfcollect` avisará e se referirá a essas instruções.</span><span class="sxs-lookup"><span data-stu-id="46e52-168">If `crossgen` is not there, `perfcollect` warns you and refers you to these instructions.</span></span> <span data-ttu-id="46e52-169">Para corrigir as coisas necessárias para buscar exatamente a versão correta do CrossGen para o tempo de execução que você está usando.</span><span class="sxs-lookup"><span data-stu-id="46e52-169">To fix things you need to fetch exactly the right version of crossgen for the runtime you are using.</span></span> <span data-ttu-id="46e52-170">Se você posicionar a ferramenta CrossGen no mesmo diretório que as DLLs de tempo de execução do .NET (por exemplo, libcoreclr.so), `perfcollect` poderá encontrá-la e adicionar os símbolos de estrutura ao arquivo de rastreamento para você.</span><span class="sxs-lookup"><span data-stu-id="46e52-170">If you place the crossgen tool in the same directory as the .NET Runtime DLLs (for example, libcoreclr.so), then `perfcollect` can find it and add the framework symbols to the trace file for you.</span></span>

<span data-ttu-id="46e52-171">Normalmente, quando você cria um aplicativo .NET, ele apenas gera a DLL para o código que você escreveu, usando uma cópia compartilhada do tempo de execução para o restante.</span><span class="sxs-lookup"><span data-stu-id="46e52-171">Normally when you create a .NET application, it just generates the DLL for the code you wrote, using a shared copy of the runtime for the rest.</span></span>   <span data-ttu-id="46e52-172">No entanto, você também pode gerar o que é chamado de uma versão ' autocontida ' de um aplicativo e isso contém todas as DLLs de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="46e52-172">However you can also generate what is called a 'self-contained' version of an application and this contains all runtime DLLs.</span></span> <span data-ttu-id="46e52-173">`crossgen` faz parte do pacote NuGet usado para criar aplicativos independentes, portanto, uma maneira de obter a versão correta do `crossgen` é criar um pacote independente de seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="46e52-173">`crossgen` is part of the NuGet package that is used to create self-contained apps, so one way of getting the right version of `crossgen` is to create a self-contained package of your application.</span></span>

<span data-ttu-id="46e52-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="46e52-174">For example:</span></span>

   >```bash
   > mkdir helloWorld
   > cd helloWorld
   > dotnet new console
   > dotnet publish --self-contained -r linux-x64
   >```

<span data-ttu-id="46e52-175">Isso cria um novo aplicativo Olá, Mundo e o compila como um aplicativo independente.</span><span class="sxs-lookup"><span data-stu-id="46e52-175">This creates a new Hello World application and builds it as a self-contained app.</span></span>

<span data-ttu-id="46e52-176">Como um efeito colateral da criação do aplicativo independente, a ferramenta dotnet baixará um pacote NuGet chamado Runtime. Linux-x64. Microsoft. NetCore. app e o coloca no diretório ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION, em que VERSION é o número de versão do seu tempo de execução do .NET Core (por exemplo, 2.1.0).</span><span class="sxs-lookup"><span data-stu-id="46e52-176">As a side effect of creating the self-contained application the dotnet tool will download a NuGet package called runtime.linux-x64.microsoft.netcore.app and place it in the directory ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION, where VERSION is the version number of your .NET Core runtime (for example, 2.1.0).</span></span> <span data-ttu-id="46e52-177">Isso é um diretório de ferramentas e, dentro daí, há a ferramenta CrossGen de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="46e52-177">Under that is a tools directory and inside there is the crossgen tool you need.</span></span> <span data-ttu-id="46e52-178">A partir do .NET Core 3,0, o local do pacote é ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION.</span><span class="sxs-lookup"><span data-stu-id="46e52-178">Starting with .NET Core 3.0, the package location is ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION.</span></span>

<span data-ttu-id="46e52-179">A `crossgen` ferramenta precisa ser colocada ao lado do tempo de execução que é realmente usado pelo seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="46e52-179">The `crossgen` tool needs to be put next to the runtime that is actually used by your application.</span></span> <span data-ttu-id="46e52-180">Normalmente, seu aplicativo usa a versão compartilhada do .NET Core que está instalada em/usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION, em que VERSION é o número de versão do tempo de execução do .NET.</span><span class="sxs-lookup"><span data-stu-id="46e52-180">Typically your app uses the shared version of .NET Core that is installed at /usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION where VERSION is the version number of the .NET Runtime.</span></span> <span data-ttu-id="46e52-181">Esse é um local compartilhado, portanto, você precisa ser um superusuário para modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="46e52-181">This is a shared location, so you need to be super-user to modify it.</span></span> <span data-ttu-id="46e52-182">Se a versão for 2.1.0, os comandos a serem atualizados `crossgen` seriam:</span><span class="sxs-lookup"><span data-stu-id="46e52-182">If the VERSION is 2.1.0 the commands to update `crossgen` would be:</span></span>

   >```bash
   > sudo bash
   > cp ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/2.1.0/tools/crossgen /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
   >```

<span data-ttu-id="46e52-183">Depois de fazer isso, o `perfcollect` usará CrossGen para incluir símbolos de estrutura.</span><span class="sxs-lookup"><span data-stu-id="46e52-183">Once you have done this, `perfcollect` will use crossgen to include framework symbols.</span></span> <span data-ttu-id="46e52-184">O aviso que `perfcollect` costumava ser emitido deve desaparecer.</span><span class="sxs-lookup"><span data-stu-id="46e52-184">The warning that `perfcollect` used to issue should go away.</span></span> <span data-ttu-id="46e52-185">Isso só precisa ser uma vez por computador (até que você atualize seu tempo de execução).</span><span class="sxs-lookup"><span data-stu-id="46e52-185">This only has to be one once per machine (until you update your runtime).</span></span>

### <a name="alternative-turn-off-use-of-precompiled-code"></a><span data-ttu-id="46e52-186">Alternativa: desativar o uso de código pré-compilado</span><span class="sxs-lookup"><span data-stu-id="46e52-186">Alternative: Turn off use of precompiled code</span></span>

<span data-ttu-id="46e52-187">Se você não tiver a capacidade de atualizar o tempo de execução do .NET (para adicionar `crossgen` ) ou se o procedimento acima não funcionou por algum motivo, há outra abordagem para obter os símbolos de estrutura.</span><span class="sxs-lookup"><span data-stu-id="46e52-187">If you don't have the ability to update the .NET Runtime (to add `crossgen`), or if the above procedure did not work for some reason, there is another approach to getting framework symbols.</span></span> <span data-ttu-id="46e52-188">Você pode dizer ao tempo de execução para simplesmente não usar o código de estrutura pré-compilado.</span><span class="sxs-lookup"><span data-stu-id="46e52-188">You can tell the runtime to simply not use the precompiled framework code.</span></span> <span data-ttu-id="46e52-189">O código será compilado just-in-time e `crossgen` não será necessário.</span><span class="sxs-lookup"><span data-stu-id="46e52-189">The code will be Just-In-Time compiled and `crossgen` is not needed.</span></span>

> [!NOTE]
> <span data-ttu-id="46e52-190">A escolha dessa abordagem pode aumentar o tempo de inicialização para seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="46e52-190">Choosing this approach may increase the startup time for your application.</span></span>

<span data-ttu-id="46e52-191">Para fazer isso, você pode adicionar a seguinte variável de ambiente:</span><span class="sxs-lookup"><span data-stu-id="46e52-191">To do this, you can add the following environment variable:</span></span>

```bash
export COMPlus_ZapDisable=1
```

<span data-ttu-id="46e52-192">Com essa alteração, você deve obter os símbolos para todo o código .NET.</span><span class="sxs-lookup"><span data-stu-id="46e52-192">With this change, you should get the symbols for all .NET code.</span></span>

## <a name="get-symbols-for-the-native-runtime"></a><span data-ttu-id="46e52-193">Obter símbolos para o tempo de execução nativo</span><span class="sxs-lookup"><span data-stu-id="46e52-193">Get symbols for the native runtime</span></span>

<span data-ttu-id="46e52-194">Na maioria das vezes, você está interessado em seu próprio código, que é `perfcollect` resolvido por padrão.</span><span class="sxs-lookup"><span data-stu-id="46e52-194">Most of the time you are interested in your own code, which `perfcollect` resolves by default.</span></span> <span data-ttu-id="46e52-195">Às vezes, é útil ver o que está acontecendo dentro das DLLs do .NET (que é a última seção sobre), mas às vezes, o que está acontecendo nas DLLs do tempo de execução nativo (normalmente libcoreclr.so) é interessante.</span><span class="sxs-lookup"><span data-stu-id="46e52-195">Sometimes it is useful to see what is going on inside the .NET DLLs (which is what the last section was about), but sometimes what is going on in the native runtime dlls (typically libcoreclr.so), is interesting.</span></span>  <span data-ttu-id="46e52-196">`perfcollect` o resolverá os símbolos para eles quando ele converter seus dados, mas somente se os símbolos para essas DLLs nativas estiverem presentes (e estiverem ao lado da biblioteca de onde estão).</span><span class="sxs-lookup"><span data-stu-id="46e52-196">`perfcollect` will resolve the symbols for these when it converts its data, but only if the symbols for these native DLLs are present (and are beside the library they are for).</span></span>

<span data-ttu-id="46e52-197">Há um comando global chamado [dotnet-símbolo](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) que faz isso.</span><span class="sxs-lookup"><span data-stu-id="46e52-197">There is a global command called [dotnet-symbol](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) that does this.</span></span> <span data-ttu-id="46e52-198">Para usar dotnet-Symbol para obter símbolos de tempo de execução nativos:</span><span class="sxs-lookup"><span data-stu-id="46e52-198">To use dotnet-symbol to get native runtime symbols:</span></span>

1. <span data-ttu-id="46e52-199">Instale `dotnet-symbol`:</span><span class="sxs-lookup"><span data-stu-id="46e52-199">Install `dotnet-symbol`:</span></span>

    ```bash
    dotnet tool install -g dotnet-symbol
    ```

2. <span data-ttu-id="46e52-200">Baixe os símbolos.</span><span class="sxs-lookup"><span data-stu-id="46e52-200">Download the symbols.</span></span> <span data-ttu-id="46e52-201">Se a versão instalada do tempo de execução do .NET Core for 2.1.0, o comando para fazer isso é:</span><span class="sxs-lookup"><span data-stu-id="46e52-201">If your installed version of the .NET Core runtime is 2.1.0, the command to do this is:</span></span>

    ```bash
    mkdir mySymbols
    dotnet symbol --symbols --output mySymbols  /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0/lib*.so
    ```

3. <span data-ttu-id="46e52-202">Copie os símbolos para o local correto.</span><span class="sxs-lookup"><span data-stu-id="46e52-202">Copy the symbols to the correct place.</span></span>

    ```bash
    sudo cp mySymbols/* /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
    ```

    <span data-ttu-id="46e52-203">Se isso não puder ser feito porque você não tem acesso de gravação ao diretório apropriado, você pode usar `perf buildid-cache` para adicionar os símbolos.</span><span class="sxs-lookup"><span data-stu-id="46e52-203">If this cannot be done because you do not have write access to the appropriate directory, you can use `perf buildid-cache` to add the symbols.</span></span>

<span data-ttu-id="46e52-204">Depois disso, você deve obter nomes simbólicos para as DLLs nativas ao executar o `perfcollect` .</span><span class="sxs-lookup"><span data-stu-id="46e52-204">After this, you should get symbolic names for the native dlls when you run `perfcollect`.</span></span>

## <a name="collect-in-a-docker-container"></a><span data-ttu-id="46e52-205">Coletar em um contêiner do Docker</span><span class="sxs-lookup"><span data-stu-id="46e52-205">Collect in a Docker container</span></span>

<span data-ttu-id="46e52-206">Para obter mais informações sobre como usar `perfcollect` em ambientes de contêiner, consulte [coletar diagnósticos em contêineres](./diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="46e52-206">For more information on how to use `perfcollect` in container environments, see [Collect diagnostics in containers](./diagnostics-in-containers.md).</span></span>

## <a name="learn-more-about-collection-options"></a><span data-ttu-id="46e52-207">Saiba mais sobre as opções de coleta</span><span class="sxs-lookup"><span data-stu-id="46e52-207">Learn more about collection options</span></span>

<span data-ttu-id="46e52-208">Você pode especificar os seguintes sinalizadores opcionais com o `perfcollect` para atender melhor às suas necessidades de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="46e52-208">You can specify the following optional flags with `perfcollect` to better suit your diagnostic needs.</span></span>

### <a name="collect-for-a-specific-duration"></a><span data-ttu-id="46e52-209">Coletar por uma duração específica</span><span class="sxs-lookup"><span data-stu-id="46e52-209">Collect for a specific duration</span></span>

<span data-ttu-id="46e52-210">Quando desejar coletar um rastreamento para uma duração específica, você poderá usar `-collectsec` a opção seguida de um número especificando o total de segundos para coletar um rastreamento.</span><span class="sxs-lookup"><span data-stu-id="46e52-210">When you want to collect a trace for a specific duration, you can use `-collectsec` option followed by a number specifying the total seconds to collect a trace for.</span></span>

### <a name="collect-threadtime-traces"></a><span data-ttu-id="46e52-211">Coletar rastreamentos de threadtime</span><span class="sxs-lookup"><span data-stu-id="46e52-211">Collect threadtime traces</span></span>

<span data-ttu-id="46e52-212">Especificar `-threadtime` with `perfcollect` permite que você colete dados de uso de CPU por thread.</span><span class="sxs-lookup"><span data-stu-id="46e52-212">Specifying `-threadtime` with `perfcollect` lets you collect per-thread CPU usage data.</span></span> <span data-ttu-id="46e52-213">Isso permite que você analise onde cada thread estava gastando seu tempo de CPU.</span><span class="sxs-lookup"><span data-stu-id="46e52-213">This lets you analyze where every thread was spending its CPU time.</span></span>

### <a name="collect-traces-for-managed-memory-and-garbage-collector-performance"></a><span data-ttu-id="46e52-214">Coletar rastreamentos para memória gerenciada e desempenho do coletor de lixo</span><span class="sxs-lookup"><span data-stu-id="46e52-214">Collect traces for managed memory and garbage collector performance</span></span>

<span data-ttu-id="46e52-215">As opções a seguir permitem que você colete especificamente os eventos de GC do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="46e52-215">The following options let you specifically collect the GC events from the runtime.</span></span>

* `perfcollect collect -gccollectonly`

<span data-ttu-id="46e52-216">Colete apenas um conjunto mínimo de eventos de coleta de GC.</span><span class="sxs-lookup"><span data-stu-id="46e52-216">Collect only a minimal set of GC Collection events.</span></span> <span data-ttu-id="46e52-217">Esse é o perfil de coleção de eventos do GC menos detalhado com o menor impacto no desempenho do aplicativo de destino.</span><span class="sxs-lookup"><span data-stu-id="46e52-217">This is the least verbose GC eventing collection profile with the lowest impact on the target app's performance.</span></span> <span data-ttu-id="46e52-218">Esse comando é análogo ao `PerfView.exe /GCCollectOnly collect` comando no Perfview.</span><span class="sxs-lookup"><span data-stu-id="46e52-218">This command is analogous to `PerfView.exe /GCCollectOnly collect` command in PerfView.</span></span>

* `perfcollect collect -gconly`

<span data-ttu-id="46e52-219">Colete eventos de coleta de GC mais detalhados com eventos JIT, Loader e Exception.</span><span class="sxs-lookup"><span data-stu-id="46e52-219">Collect more verbose GC collection events with JIT, Loader, and Exception events.</span></span> <span data-ttu-id="46e52-220">Isso solicita eventos mais detalhados (como as informações de alocação e informações de ingresso no GC) e terá mais impacto na opção desempenho do aplicativo de destino do que `-gccollectonly` .</span><span class="sxs-lookup"><span data-stu-id="46e52-220">This requests more verbose events (such as the allocation information and GC join information) and will have more impact to the target app's performance than `-gccollectonly` option.</span></span> <span data-ttu-id="46e52-221">Esse comando é análogo ao `PerfView.exe /GCOnly collect` comando no Perfview.</span><span class="sxs-lookup"><span data-stu-id="46e52-221">This command is analogous to `PerfView.exe /GCOnly collect` command in PerfView.</span></span>

* `perfcollect collect -gcwithheap`

<span data-ttu-id="46e52-222">Colete os eventos de coleta de GC mais detalhados que controlam a sobrevivência e os movimentos de heap também.</span><span class="sxs-lookup"><span data-stu-id="46e52-222">Collect the most verbose GC collection events which tracks the heap survival and movements as well.</span></span> <span data-ttu-id="46e52-223">Isso fornece uma análise detalhada do comportamento do GC, mas incorrerá em custo de alto desempenho, já que cada GC pode levar mais de duas vezes mais.</span><span class="sxs-lookup"><span data-stu-id="46e52-223">This gives in-depth analysis of the GC behavior but will incur high performance cost as each GC can take more than two times longer.</span></span> <span data-ttu-id="46e52-224">É recomendável que você entenda a implicação de desempenho do uso dessa opção de rastreamento ao rastrear em ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="46e52-224">It is recommended you understand the performance implication of using this trace option when tracing in production environments.</span></span>
