---
title: dotnet-ferramenta de diagnóstico de rastreamento-CLI do .NET
description: Saiba como instalar e usar a ferramenta de CLI de rastreamento dotnet para coletar rastreamentos do .NET de um processo em execução sem o criador de perfil nativo, usando o .NET EventPipe.
ms.date: 11/17/2020
ms.openlocfilehash: a3b5748cb2a6c2060971fbad0d81ade00dc83087
ms.sourcegitcommit: 35ca2255c6c86968eaef9e3a251c9739ce8e4288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/23/2020
ms.locfileid: "97753659"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="10e25-103">dotnet-utilitário de análise de desempenho de rastreamento</span><span class="sxs-lookup"><span data-stu-id="10e25-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="10e25-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="10e25-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="10e25-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="10e25-105">Install</span></span>

<span data-ttu-id="10e25-106">Há duas maneiras de baixar e instalar `dotnet-trace` :</span><span class="sxs-lookup"><span data-stu-id="10e25-106">There are two ways to download and install `dotnet-trace`:</span></span>

- <span data-ttu-id="10e25-107">**ferramenta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="10e25-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="10e25-108">Para instalar a versão de lançamento mais recente do `dotnet-trace` [pacote NuGet](https://www.nuget.org/packages/dotnet-trace), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="10e25-108">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- <span data-ttu-id="10e25-109">**Download direto:**</span><span class="sxs-lookup"><span data-stu-id="10e25-109">**Direct download:**</span></span>

  <span data-ttu-id="10e25-110">Baixe o executável da ferramenta que corresponde à sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="10e25-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="10e25-111">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="10e25-111">OS</span></span>  | <span data-ttu-id="10e25-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="10e25-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="10e25-113">Windows</span><span class="sxs-lookup"><span data-stu-id="10e25-113">Windows</span></span> | <span data-ttu-id="10e25-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [ARM](https://aka.ms/dotnet-trace/win-arm) \| [ARM-x64](https://aka.ms/dotnet-trace/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="10e25-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span></span> |
  | <span data-ttu-id="10e25-115">macOS</span><span class="sxs-lookup"><span data-stu-id="10e25-115">macOS</span></span>   | [<span data-ttu-id="10e25-116">x64</span><span class="sxs-lookup"><span data-stu-id="10e25-116">x64</span></span>](https://aka.ms/dotnet-trace/osx-x64) |
  | <span data-ttu-id="10e25-117">Linux</span><span class="sxs-lookup"><span data-stu-id="10e25-117">Linux</span></span>   | <span data-ttu-id="10e25-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [ARM](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [MUSL-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [MUSL-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="10e25-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="10e25-119">Sinopse</span><span class="sxs-lookup"><span data-stu-id="10e25-119">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="10e25-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="10e25-120">Description</span></span>

<span data-ttu-id="10e25-121">A `dotnet-trace` ferramenta:</span><span class="sxs-lookup"><span data-stu-id="10e25-121">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="10e25-122">É uma ferramenta .NET Core de plataforma cruzada.</span><span class="sxs-lookup"><span data-stu-id="10e25-122">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="10e25-123">Habilita a coleção de rastreamentos do .NET Core de um processo em execução sem um criador de perfil nativo.</span><span class="sxs-lookup"><span data-stu-id="10e25-123">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="10e25-124">É criado [`EventPipe`](./eventpipe.md) a partir do tempo de execução do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="10e25-124">Is built on [`EventPipe`](./eventpipe.md) of the .NET Core runtime.</span></span>
* <span data-ttu-id="10e25-125">Oferece a mesma experiência no Windows, Linux ou macOS.</span><span class="sxs-lookup"><span data-stu-id="10e25-125">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="10e25-126">Opções</span><span class="sxs-lookup"><span data-stu-id="10e25-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="10e25-127">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="10e25-127">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="10e25-128">Exibe a versão do utilitário dotnet-Trace.</span><span class="sxs-lookup"><span data-stu-id="10e25-128">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="10e25-129">Comandos</span><span class="sxs-lookup"><span data-stu-id="10e25-129">Commands</span></span>

| <span data-ttu-id="10e25-130">Comando</span><span class="sxs-lookup"><span data-stu-id="10e25-130">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="10e25-131">dotnet-coleta de rastreamento</span><span class="sxs-lookup"><span data-stu-id="10e25-131">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="10e25-132">dotnet-conversão de rastreamento</span><span class="sxs-lookup"><span data-stu-id="10e25-132">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="10e25-133">dotnet-rastrear PS</span><span class="sxs-lookup"><span data-stu-id="10e25-133">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="10e25-134">dotnet-lista de rastreamento-perfis</span><span class="sxs-lookup"><span data-stu-id="10e25-134">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="10e25-135">dotnet-coleta de rastreamento</span><span class="sxs-lookup"><span data-stu-id="10e25-135">dotnet-trace collect</span></span>

<span data-ttu-id="10e25-136">Coleta um rastreamento de diagnóstico de um processo em execução.</span><span class="sxs-lookup"><span data-stu-id="10e25-136">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="10e25-137">Sinopse</span><span class="sxs-lookup"><span data-stu-id="10e25-137">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>] [--diagnostic-port] [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="10e25-138">Opções</span><span class="sxs-lookup"><span data-stu-id="10e25-138">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="10e25-139">Define o tamanho do buffer circular na memória, em megabytes.</span><span class="sxs-lookup"><span data-stu-id="10e25-139">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="10e25-140">256 MB padrão.</span><span class="sxs-lookup"><span data-stu-id="10e25-140">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="10e25-141">Detalhes dos eventos CLR a serem emitidos.</span><span class="sxs-lookup"><span data-stu-id="10e25-141">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="10e25-142">Lista de eventos de tempo de execução CLR a serem emitidos.</span><span class="sxs-lookup"><span data-stu-id="10e25-142">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="10e25-143">Define o formato de saída para a conversão do arquivo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="10e25-143">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="10e25-144">O padrão é `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="10e25-144">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="10e25-145">O nome do processo do qual coletar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="10e25-145">The name of the process to collect the trace from.</span></span>

- **`--diagnostic-port <path-to-port>`**

  <span data-ttu-id="10e25-146">O nome da porta de diagnóstico a ser criada.</span><span class="sxs-lookup"><span data-stu-id="10e25-146">The name of the diagnostic port to create.</span></span> <span data-ttu-id="10e25-147">Consulte [usar a porta de diagnóstico para coletar um rastreamento da inicialização do aplicativo](#use-diagnostic-port-to-collect-a-trace-from-app-startup) para saber como usar essa opção para coletar um rastreamento da inicialização do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="10e25-147">See [Use diagnostic port to collect a trace from app startup](#use-diagnostic-port-to-collect-a-trace-from-app-startup) to learn how to use this option to collect a trace from app startup.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="10e25-148">O caminho de saída para os dados de rastreamento coletados.</span><span class="sxs-lookup"><span data-stu-id="10e25-148">The output path for the collected trace data.</span></span> <span data-ttu-id="10e25-149">Se não for especificado, o padrão será `trace.nettrace` .</span><span class="sxs-lookup"><span data-stu-id="10e25-149">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="10e25-150">A ID do processo da qual coletar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="10e25-150">The process ID to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="10e25-151">Um conjunto nomeado predefinido de configurações de provedor que permite que cenários de rastreamento comuns sejam especificados de forma sucinta.</span><span class="sxs-lookup"><span data-stu-id="10e25-151">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span> <span data-ttu-id="10e25-152">Os seguintes perfis estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="10e25-152">The following profiles are available:</span></span>

 | <span data-ttu-id="10e25-153">Perfil</span><span class="sxs-lookup"><span data-stu-id="10e25-153">Profile</span></span> | <span data-ttu-id="10e25-154">Descrição</span><span class="sxs-lookup"><span data-stu-id="10e25-154">Description</span></span> |
 |---------|-------------|
 |`cpu-sampling`|<span data-ttu-id="10e25-155">Útil para controlar o uso da CPU e informações gerais de tempo de execução do .NET.</span><span class="sxs-lookup"><span data-stu-id="10e25-155">Useful for tracking CPU usage and general .NET runtime information.</span></span> <span data-ttu-id="10e25-156">Essa será a opção padrão se nenhum perfil ou provedor for especificado.</span><span class="sxs-lookup"><span data-stu-id="10e25-156">This is the default option if no profile or providers are specified.</span></span>|
 |`gc-verbose`|<span data-ttu-id="10e25-157">Rastreia coleções de GC e as alocações de objeto de exemplos.</span><span class="sxs-lookup"><span data-stu-id="10e25-157">Tracks GC collections and samples object allocations.</span></span>|
 |`gc-collect`|<span data-ttu-id="10e25-158">Rastreia coleções de GC somente em sobrecarga muito baixa.</span><span class="sxs-lookup"><span data-stu-id="10e25-158">Tracks GC collections only at very low overhead.</span></span>|

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="10e25-159">Uma lista separada por vírgulas de `EventPipe` provedores a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="10e25-159">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="10e25-160">Esses provedores complementam todos os provedores implícitos pelo `--profile <profile-name>` .</span><span class="sxs-lookup"><span data-stu-id="10e25-160">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="10e25-161">Se houver alguma inconsistência para um provedor específico, essa configuração terá precedência sobre a configuração implícita do perfil.</span><span class="sxs-lookup"><span data-stu-id="10e25-161">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="10e25-162">Esta lista de provedores está no formato:</span><span class="sxs-lookup"><span data-stu-id="10e25-162">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="10e25-163">`Provider` está no formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]` .</span><span class="sxs-lookup"><span data-stu-id="10e25-163">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="10e25-164">`KeyValueArgs` está no formato: `[key1=value1][;key2=value2]` .</span><span class="sxs-lookup"><span data-stu-id="10e25-164">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="10e25-165">**`-- <command>` (somente para aplicativos de destino que executam o .NET 5,0)**</span><span class="sxs-lookup"><span data-stu-id="10e25-165">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="10e25-166">Após os parâmetros de configuração da coleção, o usuário pode acrescentar `--` seguido por um comando para iniciar um aplicativo .NET com pelo menos um tempo de execução de 5,0.</span><span class="sxs-lookup"><span data-stu-id="10e25-166">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="10e25-167">Isso pode ser útil ao diagnosticar problemas que ocorrem no início do processo, como problemas de desempenho de inicialização ou carregador de assembly e erros de fichário.</span><span class="sxs-lookup"><span data-stu-id="10e25-167">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="10e25-168">O uso dessa opção monitora o primeiro processo do .NET 5,0 que se comunica de volta à ferramenta, o que significa que, se o comando iniciar vários aplicativos .NET, ele só coletará o primeiro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="10e25-168">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="10e25-169">Portanto, é recomendável usar essa opção em aplicativos independentes ou usando a `dotnet exec <app.dll>` opção.</span><span class="sxs-lookup"><span data-stu-id="10e25-169">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-170">Parar o rastreamento pode levar muito tempo (até minutos) para aplicativos grandes.</span><span class="sxs-lookup"><span data-stu-id="10e25-170">Stopping the trace may take a long time (up to minutes) for large applications.</span></span> <span data-ttu-id="10e25-171">O tempo de execução precisa enviar pelo cache de tipo para todo o código gerenciado que foi capturado no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="10e25-171">The runtime needs to send over the type cache for all managed code that was captured in the trace.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="10e25-172">dotnet-conversão de rastreamento</span><span class="sxs-lookup"><span data-stu-id="10e25-172">dotnet-trace convert</span></span>

<span data-ttu-id="10e25-173">Converte `nettrace` rastreamentos em formatos alternativos para uso com ferramentas de análise de rastreamento alternativas.</span><span class="sxs-lookup"><span data-stu-id="10e25-173">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="10e25-174">Sinopse</span><span class="sxs-lookup"><span data-stu-id="10e25-174">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="10e25-175">Argumentos</span><span class="sxs-lookup"><span data-stu-id="10e25-175">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="10e25-176">Arquivo de rastreamento de entrada a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="10e25-176">Input trace file to be converted.</span></span> <span data-ttu-id="10e25-177">O padrão é *trace. NetTrace*.</span><span class="sxs-lookup"><span data-stu-id="10e25-177">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="10e25-178">Opções</span><span class="sxs-lookup"><span data-stu-id="10e25-178">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="10e25-179">Define o formato de saída para a conversão do arquivo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="10e25-179">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="10e25-180">Nome de arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="10e25-180">Output filename.</span></span> <span data-ttu-id="10e25-181">A extensão do formato de destino será adicionada.</span><span class="sxs-lookup"><span data-stu-id="10e25-181">Extension of target format will be added.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-182">`nettrace`A conversão de arquivos em `chromium` ou `speedscope` arquivos é irreversível.</span><span class="sxs-lookup"><span data-stu-id="10e25-182">Converting `nettrace` files to `chromium` or `speedscope` files is irreversible.</span></span> <span data-ttu-id="10e25-183">`speedscope` e `chromium` os arquivos não têm todas as informações necessárias para reconstruir os `nettrace` arquivos.</span><span class="sxs-lookup"><span data-stu-id="10e25-183">`speedscope` and `chromium` files don't have all the information necessary to reconstruct `nettrace` files.</span></span> <span data-ttu-id="10e25-184">No entanto, o `convert` comando preserva o `nettrace` arquivo original, portanto, não exclua esse arquivo se você planeja abri-lo no futuro.</span><span class="sxs-lookup"><span data-stu-id="10e25-184">However, the `convert` command preserves the original `nettrace` file, so don't delete this file if you plan to open it in the future.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="10e25-185">dotnet-rastrear PS</span><span class="sxs-lookup"><span data-stu-id="10e25-185">dotnet-trace ps</span></span>

 <span data-ttu-id="10e25-186">Lista os processos dotnet dos quais os rastreamentos podem ser coletados.</span><span class="sxs-lookup"><span data-stu-id="10e25-186">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="10e25-187">Sinopse</span><span class="sxs-lookup"><span data-stu-id="10e25-187">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="10e25-188">dotnet-lista de rastreamento-perfis</span><span class="sxs-lookup"><span data-stu-id="10e25-188">dotnet-trace list-profiles</span></span>

<span data-ttu-id="10e25-189">Lista os perfis de rastreamento pré-criados com uma descrição de quais provedores e filtros estão em cada perfil.</span><span class="sxs-lookup"><span data-stu-id="10e25-189">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="10e25-190">Sinopse</span><span class="sxs-lookup"><span data-stu-id="10e25-190">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="10e25-191">Coletar um rastreamento com dotnet-Trace</span><span class="sxs-lookup"><span data-stu-id="10e25-191">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="10e25-192">Para coletar rastreamentos usando `dotnet-trace` :</span><span class="sxs-lookup"><span data-stu-id="10e25-192">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="10e25-193">Obtenha o identificador do processo (PID) do aplicativo .NET Core do qual coletar rastreamentos.</span><span class="sxs-lookup"><span data-stu-id="10e25-193">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="10e25-194">No Windows, você pode usar o Gerenciador de tarefas ou o `tasklist` comando, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="10e25-194">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="10e25-195">No Linux, por exemplo, o `ps` comando.</span><span class="sxs-lookup"><span data-stu-id="10e25-195">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="10e25-196">dotnet-rastrear PS</span><span class="sxs-lookup"><span data-stu-id="10e25-196">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="10e25-197">Execute o comando a seguir:</span><span class="sxs-lookup"><span data-stu-id="10e25-197">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="10e25-198">O comando anterior gera uma saída semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="10e25-198">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="10e25-199">Pare a coleta pressionando a `<Enter>` tecla.</span><span class="sxs-lookup"><span data-stu-id="10e25-199">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="10e25-200">`dotnet-trace` encerrará eventos de log no arquivo *trace. NetTrace* .</span><span class="sxs-lookup"><span data-stu-id="10e25-200">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="10e25-201">Iniciar um aplicativo filho e coletar um rastreamento de sua inicialização usando dotNet-Trace</span><span class="sxs-lookup"><span data-stu-id="10e25-201">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10e25-202">Isso funciona somente para aplicativos que executam o .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="10e25-202">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="10e25-203">Às vezes, pode ser útil coletar um rastreamento de um processo a partir de sua inicialização.</span><span class="sxs-lookup"><span data-stu-id="10e25-203">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="10e25-204">Para aplicativos que executam o .NET 5,0 ou posterior, é possível fazer isso usando o rastreamento dotnet.</span><span class="sxs-lookup"><span data-stu-id="10e25-204">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="10e25-205">Isso será iniciado `hello.exe` com `arg1` e `arg2` como seus argumentos de linha de comando e coletará um rastreamento de sua inicialização de tempo de execução:</span><span class="sxs-lookup"><span data-stu-id="10e25-205">This will launch `hello.exe` with `arg1` and `arg2` as its command-line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="10e25-206">O comando anterior gera uma saída semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="10e25-206">The preceding command generates output similar to the following:</span></span>

```console
No profile or providers specified, defaulting to trace profile 'cpu-sampling'

Provider Name                           Keywords            Level               Enabled By
Microsoft-DotNETCore-SampleProfiler     0x0000F00000000000  Informational(4)    --profile
Microsoft-Windows-DotNETRuntime         0x00000014C14FCCBD  Informational(4)    --profile

Process        : E:\temp\gcperfsim\bin\Debug\net5.0\gcperfsim.exe
Output File    : E:\temp\gcperfsim\trace.nettrace


[00:00:00:05]   Recording trace 122.244  (KB)
Press <Enter> or <Ctrl+C> to exit...
```

<span data-ttu-id="10e25-207">Você pode parar de coletar o rastreamento pressionando `<Enter>` ou `<Ctrl + C>` tecla.</span><span class="sxs-lookup"><span data-stu-id="10e25-207">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="10e25-208">Isso também será encerrado `hello.exe` .</span><span class="sxs-lookup"><span data-stu-id="10e25-208">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-209">`hello.exe`A inicialização por meio de dotnet-Trace fará com que sua entrada/saída seja redirecionada e você não conseguirá interagir com seu STDIN/STDOUT.</span><span class="sxs-lookup"><span data-stu-id="10e25-209">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="10e25-210">Sair da ferramenta por meio de CTRL + C ou SIGTERM irá encerrar com segurança a ferramenta e o processo filho.</span><span class="sxs-lookup"><span data-stu-id="10e25-210">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="10e25-211">Se o processo filho for encerrado antes da ferramenta, a ferramenta também será encerrada e o rastreamento deverá ser visível com segurança.</span><span class="sxs-lookup"><span data-stu-id="10e25-211">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="use-diagnostic-port-to-collect-a-trace-from-app-startup"></a><span data-ttu-id="10e25-212">Usar a porta de diagnóstico para coletar um rastreamento da inicialização do aplicativo</span><span class="sxs-lookup"><span data-stu-id="10e25-212">Use diagnostic port to collect a trace from app startup</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="10e25-213">Isso funciona somente para aplicativos que executam o .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="10e25-213">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="10e25-214">A porta de diagnóstico é um novo recurso de tempo de execução que foi adicionado no .NET 5 que permite iniciar o rastreamento da inicialização do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="10e25-214">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start tracing from app startup.</span></span> <span data-ttu-id="10e25-215">Para fazer isso usando o `dotnet-trace` , você pode usar o `dotnet-trace collect -- <command>` conforme descrito nos exemplos acima ou usar a `--diagnostic-port` opção.</span><span class="sxs-lookup"><span data-stu-id="10e25-215">To do this using `dotnet-trace`, you can either use `dotnet-trace collect -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="10e25-216">Usar o `dotnet-trace <collect|monitor> -- <command>` para iniciar o aplicativo como um processo filho é a maneira mais simples de rastreá-lo rapidamente a partir de sua inicialização.</span><span class="sxs-lookup"><span data-stu-id="10e25-216">Using `dotnet-trace <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly trace it from its startup.</span></span>

<span data-ttu-id="10e25-217">No entanto, quando você quiser obter um controle mais preciso sobre o tempo de vida do aplicativo que está sendo rastreado (por exemplo, monitorar o aplicativo pelos primeiros 10 minutos apenas e continuar executando) ou se precisar interagir com o aplicativo usando a CLI, o uso da `--diagnostic-port` opção permitirá que você controle o aplicativo de destino que está sendo monitorado e `dotnet-trace` .</span><span class="sxs-lookup"><span data-stu-id="10e25-217">However, when you want to gain a finer control over the lifetime of the app being traced (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-trace`.</span></span>

1. <span data-ttu-id="10e25-218">O comando a seguir `dotnet-trace` cria um soquete de diagnóstico chamado `myport.sock` e aguarda uma conexão.</span><span class="sxs-lookup"><span data-stu-id="10e25-218">The command below makes `dotnet-trace` create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-trace collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="10e25-219">Saída:</span><span class="sxs-lookup"><span data-stu-id="10e25-219">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="10e25-220">Em um console separado, inicie o aplicativo de destino com a variável de ambiente `DOTNET_DiagnosticPorts` definida como o valor na `dotnet-trace` saída.</span><span class="sxs-lookup"><span data-stu-id="10e25-220">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-trace` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="10e25-221">Isso deve, então, habilitar `dotnet-trace` para iniciar o rastreamento `my-dotnet-app` :</span><span class="sxs-lookup"><span data-stu-id="10e25-221">This should then enable `dotnet-trace` to start tracing `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="10e25-222">Iniciar seu aplicativo com `dotnet run` pode ser problemático porque a CLI dotnet pode gerar muitos processos filho que não são seu aplicativo e podem se conectar `dotnet-trace` antes do seu aplicativo, deixando seu aplicativo para ser suspenso em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="10e25-222">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-trace` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="10e25-223">É recomendável que você use diretamente uma versão independente do aplicativo ou use `dotnet exec` para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="10e25-223">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="10e25-224">Exibir o rastreamento capturado de dotnet-Trace</span><span class="sxs-lookup"><span data-stu-id="10e25-224">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="10e25-225">No Windows, os arquivos *. NetTrace* podem ser exibidos em [Perfview](https://github.com/microsoft/perfview) para análise: para rastreamentos coletados em outras plataformas, o arquivo de rastreamento pode ser movido para um computador Windows para ser exibido em Perfview.</span><span class="sxs-lookup"><span data-stu-id="10e25-225">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="10e25-226">No Linux, o rastreamento pode ser exibido alterando o formato de saída de `dotnet-trace` para `speedscope` .</span><span class="sxs-lookup"><span data-stu-id="10e25-226">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="10e25-227">O formato do arquivo de saída pode ser alterado usando a `-f|--format` opção- `-f speedscope` fará com que o `dotnet-trace` produza um `speedscope` arquivo.</span><span class="sxs-lookup"><span data-stu-id="10e25-227">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="10e25-228">Você pode escolher entre `nettrace` (a opção padrão) e `speedscope` .</span><span class="sxs-lookup"><span data-stu-id="10e25-228">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="10e25-229">`Speedscope` os arquivos podem ser abertos em <https://www.speedscope.app> .</span><span class="sxs-lookup"><span data-stu-id="10e25-229">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-230">O tempo de execução do .NET Core gera rastreamentos no `nettrace` formato.</span><span class="sxs-lookup"><span data-stu-id="10e25-230">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="10e25-231">Os rastreamentos são convertidos em speedscope (se especificado) após a conclusão do rastreamento.</span><span class="sxs-lookup"><span data-stu-id="10e25-231">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="10e25-232">Como algumas conversões podem resultar em perda de dados, o arquivo original `nettrace` é preservado ao lado do arquivo convertido.</span><span class="sxs-lookup"><span data-stu-id="10e25-232">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="10e25-233">Usar o rastreamento dotnet para coletar valores de contador ao longo do tempo</span><span class="sxs-lookup"><span data-stu-id="10e25-233">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="10e25-234">`dotnet-trace` podem</span><span class="sxs-lookup"><span data-stu-id="10e25-234">`dotnet-trace` can:</span></span>

* <span data-ttu-id="10e25-235">Use `EventCounter` para o monitoramento de integridade básico em ambientes sensíveis ao desempenho.</span><span class="sxs-lookup"><span data-stu-id="10e25-235">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="10e25-236">Por exemplo, em produção.</span><span class="sxs-lookup"><span data-stu-id="10e25-236">For example, in production.</span></span>
* <span data-ttu-id="10e25-237">Colete rastreamentos para que eles não precisem ser exibidos em tempo real.</span><span class="sxs-lookup"><span data-stu-id="10e25-237">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="10e25-238">Por exemplo, para coletar valores de contador de desempenho de tempo de execução, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="10e25-238">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="10e25-239">O comando anterior informa os contadores de tempo de execução para relatar uma vez a cada segundo para monitoramento de integridade leve.</span><span class="sxs-lookup"><span data-stu-id="10e25-239">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="10e25-240">Substituir `EventCounterIntervalSec=1` por um valor mais alto (por exemplo, 60) permite a coleta de um rastreamento menor com menos granularidade nos dados do contador.</span><span class="sxs-lookup"><span data-stu-id="10e25-240">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="10e25-241">O comando a seguir reduz a sobrecarga e o tamanho do rastreamento mais do que o anterior:</span><span class="sxs-lookup"><span data-stu-id="10e25-241">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="10e25-242">O comando anterior desabilita os eventos de tempo de execução e o profiler de pilha gerenciado.</span><span class="sxs-lookup"><span data-stu-id="10e25-242">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="use-rsp-file-to-avoid-typing-long-commands"></a><span data-ttu-id="10e25-243">Use o arquivo. rsp para evitar a digitação de comandos longos</span><span class="sxs-lookup"><span data-stu-id="10e25-243">Use .rsp file to avoid typing long commands</span></span>

<span data-ttu-id="10e25-244">Você pode iniciar `dotnet-trace` com um `.rsp` arquivo que contém os argumentos a serem aprovados.</span><span class="sxs-lookup"><span data-stu-id="10e25-244">You can launch `dotnet-trace` with an `.rsp` file that contains the arguments to pass.</span></span> <span data-ttu-id="10e25-245">Isso pode ser útil ao habilitar provedores que esperam argumentos longos ou ao usar um ambiente de shell que retira caracteres.</span><span class="sxs-lookup"><span data-stu-id="10e25-245">This can be useful when enabling providers that expect lengthy arguments or when using a shell environment that strips characters.</span></span>

<span data-ttu-id="10e25-246">Por exemplo, o provedor a seguir pode ser trabalhoso para digitar cada vez que você quiser rastrear:</span><span class="sxs-lookup"><span data-stu-id="10e25-246">For example, the following provider can be cumbersome to type out each time you want to trace:</span></span>

```cmd
dotnet-trace collect --providers Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="10e25-247">Além disso, o exemplo anterior contém `"` como parte do argumento.</span><span class="sxs-lookup"><span data-stu-id="10e25-247">In addition, the previous example contains `"` as part of the argument.</span></span> <span data-ttu-id="10e25-248">Como as aspas não são manipuladas igualmente por cada shell, você pode enfrentar vários problemas ao usar shells diferentes.</span><span class="sxs-lookup"><span data-stu-id="10e25-248">Because quotes are not handled equally by each shell, you may experience various issues when using different shells.</span></span> <span data-ttu-id="10e25-249">Por exemplo, o comando a ser inserido `zsh` é diferente do comando no `cmd` .</span><span class="sxs-lookup"><span data-stu-id="10e25-249">For example, the command to enter in `zsh` is different to the command in `cmd`.</span></span>

<span data-ttu-id="10e25-250">Em vez de digitar isso todas as vezes, você pode salvar o texto a seguir em um arquivo chamado `myprofile.rsp` .</span><span class="sxs-lookup"><span data-stu-id="10e25-250">Instead of typing this each time, you can save the following text into a file called `myprofile.rsp`.</span></span>

```txt
--providers
Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="10e25-251">Depois `myprofile.rsp` de salvar, você pode iniciar `dotnet-trace` com essa configuração usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="10e25-251">Once you've saved `myprofile.rsp`, you can launch `dotnet-trace` with this configuration using the following command:</span></span>

```bash
dotnet-trace @myprofile.rsp
```

## <a name="see-also"></a><span data-ttu-id="10e25-252">Veja também</span><span class="sxs-lookup"><span data-stu-id="10e25-252">See also</span></span>

- [<span data-ttu-id="10e25-253">Provedores de eventos bem conhecidos do .NET</span><span class="sxs-lookup"><span data-stu-id="10e25-253">Well-known event providers from .NET</span></span>](well-known-event-providers.md)
