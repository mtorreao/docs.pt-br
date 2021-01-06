---
title: dotnet – ferramenta de diagnóstico de despejo-CLI do .NET
description: Saiba como instalar e usar a ferramenta de CLI de despejo de dotnet para coletar e analisar despejos do Windows e do Linux sem nenhum depurador nativo.
ms.date: 11/17/2020
ms.openlocfilehash: eaffbb1f2959dba5c25a603b6f785c7480e4a8c0
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/24/2020
ms.locfileid: "97765040"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="348dc-103">Utilitário de coleta e análise de despejo (dotNet-dump)</span><span class="sxs-lookup"><span data-stu-id="348dc-103">Dump collection and analysis utility (dotnet-dump)</span></span>

<span data-ttu-id="348dc-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="348dc-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="348dc-105">`dotnet-dump` para macOS só é compatível com o .NET 5,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="348dc-105">`dotnet-dump` for macOS is only supported with .NET 5.0 and later versions.</span></span>

## <a name="install"></a><span data-ttu-id="348dc-106">Instalar</span><span class="sxs-lookup"><span data-stu-id="348dc-106">Install</span></span>

<span data-ttu-id="348dc-107">Há duas maneiras de baixar e instalar `dotnet-dump` :</span><span class="sxs-lookup"><span data-stu-id="348dc-107">There are two ways to download and install `dotnet-dump`:</span></span>

- <span data-ttu-id="348dc-108">**ferramenta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="348dc-108">**dotnet global tool:**</span></span>

  <span data-ttu-id="348dc-109">Para instalar a versão de lançamento mais recente do `dotnet-dump` [pacote NuGet](https://www.nuget.org/packages/dotnet-dump), use o comando de [instalação da ferramenta dotnet](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="348dc-109">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-dump
  ```

- <span data-ttu-id="348dc-110">**Download direto:**</span><span class="sxs-lookup"><span data-stu-id="348dc-110">**Direct download:**</span></span>

  <span data-ttu-id="348dc-111">Baixe o executável da ferramenta que corresponde à sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="348dc-111">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="348dc-112">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="348dc-112">OS</span></span>  | <span data-ttu-id="348dc-113">Plataforma</span><span class="sxs-lookup"><span data-stu-id="348dc-113">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="348dc-114">Windows</span><span class="sxs-lookup"><span data-stu-id="348dc-114">Windows</span></span> | <span data-ttu-id="348dc-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [ARM](https://aka.ms/dotnet-dump/win-arm) \| [ARM-x64](https://aka.ms/dotnet-dump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="348dc-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64)</span></span> |
  | <span data-ttu-id="348dc-116">macOS</span><span class="sxs-lookup"><span data-stu-id="348dc-116">macOS</span></span>   | [<span data-ttu-id="348dc-117">x64</span><span class="sxs-lookup"><span data-stu-id="348dc-117">x64</span></span>](https://aka.ms/dotnet-dump/osx-x64) |
  | <span data-ttu-id="348dc-118">Linux</span><span class="sxs-lookup"><span data-stu-id="348dc-118">Linux</span></span>   | <span data-ttu-id="348dc-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [ARM](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [MUSL-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [MUSL-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="348dc-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="348dc-120">Sinopse</span><span class="sxs-lookup"><span data-stu-id="348dc-120">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="348dc-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="348dc-121">Description</span></span>

<span data-ttu-id="348dc-122">A `dotnet-dump` ferramenta global é uma maneira de coletar e analisar despejos do Windows e do Linux sem nenhum depurador nativo envolvido como `lldb` no Linux.</span><span class="sxs-lookup"><span data-stu-id="348dc-122">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="348dc-123">Essa ferramenta é importante em plataformas como o Alpine Linux, onde um trabalho completo `lldb` não está disponível.</span><span class="sxs-lookup"><span data-stu-id="348dc-123">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="348dc-124">A `dotnet-dump` ferramenta permite que você execute comandos SOS para analisar falhas e o GC (coletor de lixo), mas não é um depurador nativo para que não haja suporte para a exibição de quadros de pilha nativos.</span><span class="sxs-lookup"><span data-stu-id="348dc-124">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="348dc-125">Opções</span><span class="sxs-lookup"><span data-stu-id="348dc-125">Options</span></span>

- **`--version`**

  <span data-ttu-id="348dc-126">Exibe a versão do utilitário dotnet-dump.</span><span class="sxs-lookup"><span data-stu-id="348dc-126">Displays the version of the dotnet-dump utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="348dc-127">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="348dc-127">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="348dc-128">Comandos</span><span class="sxs-lookup"><span data-stu-id="348dc-128">Commands</span></span>

| <span data-ttu-id="348dc-129">Comando</span><span class="sxs-lookup"><span data-stu-id="348dc-129">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="348dc-130">dotnet-despejo de coleta</span><span class="sxs-lookup"><span data-stu-id="348dc-130">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="348dc-131">dotnet-análise de despejo</span><span class="sxs-lookup"><span data-stu-id="348dc-131">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="348dc-132">dotnet-despejo de coleta</span><span class="sxs-lookup"><span data-stu-id="348dc-132">dotnet-dump collect</span></span>

<span data-ttu-id="348dc-133">Captura um despejo de um processo.</span><span class="sxs-lookup"><span data-stu-id="348dc-133">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="348dc-134">Sinopse</span><span class="sxs-lookup"><span data-stu-id="348dc-134">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [-n|--name] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="348dc-135">Opções</span><span class="sxs-lookup"><span data-stu-id="348dc-135">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="348dc-136">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="348dc-136">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="348dc-137">Especifica o número de identificação do processo do qual coletar um despejo.</span><span class="sxs-lookup"><span data-stu-id="348dc-137">Specifies the process ID number to collect a dump from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="348dc-138">Especifica o nome do processo do qual coletar um despejo.</span><span class="sxs-lookup"><span data-stu-id="348dc-138">Specifies the name of the process to collect a dump from.</span></span>

- **`--type <Full|Heap|Mini>`**

  <span data-ttu-id="348dc-139">Especifica o tipo de despejo, que determina os tipos de informações que são coletadas do processo.</span><span class="sxs-lookup"><span data-stu-id="348dc-139">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="348dc-140">Há três tipos:</span><span class="sxs-lookup"><span data-stu-id="348dc-140">There are three types:</span></span>

  - <span data-ttu-id="348dc-141">`Full` -O maior despejo que contém toda a memória, incluindo as imagens de módulo.</span><span class="sxs-lookup"><span data-stu-id="348dc-141">`Full` - The largest dump containing all memory including the module images.</span></span>
  - <span data-ttu-id="348dc-142">`Heap` -Um despejo grande e relativamente abrangente contendo listas de módulos, listas de threads, todas as pilhas, informações de exceção, informações de identificador e toda a memória, exceto imagens mapeadas.</span><span class="sxs-lookup"><span data-stu-id="348dc-142">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="348dc-143">`Mini` -Um despejo pequeno contendo listas de módulos, listas de threads, informações de exceção e todas as pilhas.</span><span class="sxs-lookup"><span data-stu-id="348dc-143">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="348dc-144">Se não for especificado, `Full` será o padrão.</span><span class="sxs-lookup"><span data-stu-id="348dc-144">If not specified, `Full` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="348dc-145">O caminho completo e o nome do arquivo em que o despejo coletado deve ser gravado.</span><span class="sxs-lookup"><span data-stu-id="348dc-145">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="348dc-146">Se não for especificado:</span><span class="sxs-lookup"><span data-stu-id="348dc-146">If not specified:</span></span>

  - <span data-ttu-id="348dc-147">O padrão é *. \ dump_YYYYMMDD_HHMMSS. dmp* no Windows.</span><span class="sxs-lookup"><span data-stu-id="348dc-147">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="348dc-148">O padrão é *./core_YYYYMMDD_HHMMSS* no Linux.</span><span class="sxs-lookup"><span data-stu-id="348dc-148">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="348dc-149">AAAAMMDD é ano/mês/dia e HHMMSS é hora/minuto/segundo.</span><span class="sxs-lookup"><span data-stu-id="348dc-149">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="348dc-150">Habilita o log de diagnóstico de coleta de despejo.</span><span class="sxs-lookup"><span data-stu-id="348dc-150">Enables dump collection diagnostic logging.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="348dc-151">dotnet-análise de despejo</span><span class="sxs-lookup"><span data-stu-id="348dc-151">dotnet-dump analyze</span></span>

<span data-ttu-id="348dc-152">Inicia um shell interativo para explorar um despejo.</span><span class="sxs-lookup"><span data-stu-id="348dc-152">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="348dc-153">O Shell aceita vários [comandos SOS](#analyze-sos-commands).</span><span class="sxs-lookup"><span data-stu-id="348dc-153">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="348dc-154">Sinopse</span><span class="sxs-lookup"><span data-stu-id="348dc-154">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="348dc-155">Argumentos</span><span class="sxs-lookup"><span data-stu-id="348dc-155">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="348dc-156">Especifica o caminho para o arquivo de despejo a ser analisado.</span><span class="sxs-lookup"><span data-stu-id="348dc-156">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="348dc-157">Opções</span><span class="sxs-lookup"><span data-stu-id="348dc-157">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="348dc-158">Especifica o [comando](#analyze-sos-commands) a ser executado no Shell em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="348dc-158">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="348dc-159">Analisar comandos SOS</span><span class="sxs-lookup"><span data-stu-id="348dc-159">Analyze SOS commands</span></span>

| <span data-ttu-id="348dc-160">Comando</span><span class="sxs-lookup"><span data-stu-id="348dc-160">Command</span></span>                             | <span data-ttu-id="348dc-161">Função</span><span class="sxs-lookup"><span data-stu-id="348dc-161">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="348dc-162">Exibe todos os comandos disponíveis</span><span class="sxs-lookup"><span data-stu-id="348dc-162">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="348dc-163">Exibe o comando especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-163">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="348dc-164">Sai do modo interativo.</span><span class="sxs-lookup"><span data-stu-id="348dc-164">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="348dc-165">Fornece um rastreamento de pilha apenas do código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="348dc-165">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="348dc-166">Lista os threads gerenciados em execução.</span><span class="sxs-lookup"><span data-stu-id="348dc-166">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="348dc-167">Exibe informações sobre máquinas de estado assíncrono no heap coletado por lixo.</span><span class="sxs-lookup"><span data-stu-id="348dc-167">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="348dc-168">Exibe detalhes sobre o assembly no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-168">Displays details about the assembly at the specified address.</span></span>                                 |
| `dumpclass <arguments>`             | <span data-ttu-id="348dc-169">Exibe informações sobre a `EEClass` estrutura no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-169">Displays information about the `EEClass` structure at the specified address.</span></span>                  |
| `dumpdelegate <arguments>`          | <span data-ttu-id="348dc-170">Exibe informações sobre o delegado no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-170">Displays information about the delegate at the specified address.</span></span>                             |
| `dumpdomain <arguments>`            | <span data-ttu-id="348dc-171">Exibe informações sobre todos os AppDomains e todos os assemblies no domínio especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-171">Displays information all the AppDomains and all assemblies within the specified domain.</span></span>       |
| `dumpheap <arguments>`              | <span data-ttu-id="348dc-172">Exibe informações sobre o heap coletado por lixo e estatísticas de coleção sobre objetos.</span><span class="sxs-lookup"><span data-stu-id="348dc-172">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="348dc-173">Exibe o MSIL (Microsoft Intermediate Language) associado a um método gerenciado.</span><span class="sxs-lookup"><span data-stu-id="348dc-173">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="348dc-174">Grava o conteúdo de um log de estresse na memória no arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-174">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="348dc-175">Exibe informações sobre a `MethodDesc` estrutura no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-175">Displays information about the `MethodDesc` structure at the specified address.</span></span>               |
| `dumpmodule <arguments>`            | <span data-ttu-id="348dc-176">Exibe informações sobre o módulo no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-176">Displays information about the module at the specified address.</span></span>                               |
| `dumpmt <arguments>`                | <span data-ttu-id="348dc-177">Exibe informações sobre o `MethodTable` no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-177">Displays information about the `MethodTable` at the specified address.</span></span>                        |
| `dumpobj <arguments>`               | <span data-ttu-id="348dc-178">Exibe informações sobre o objeto no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-178">Displays info about the object at the specified address.</span></span>                                      |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="348dc-179">Exibe todos os objetos gerenciados encontradas dentro dos limites da pilha atual.</span><span class="sxs-lookup"><span data-stu-id="348dc-179">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="348dc-180">Exibe informações sobre a memória de processo consumida por estruturas de dados de tempo de execução internas.</span><span class="sxs-lookup"><span data-stu-id="348dc-180">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="348dc-181">Exibe todos os objetos registrados para a finalização.</span><span class="sxs-lookup"><span data-stu-id="348dc-181">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="348dc-182">Exibe informações sobre referências (ou raízes) para o objeto no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-182">Displays info about references (or roots) to the object at the specified address.</span></span>             |
| `gcwhere <arguments>`               | <span data-ttu-id="348dc-183">Exibe o local no heap de GC do argumento passado.</span><span class="sxs-lookup"><span data-stu-id="348dc-183">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="348dc-184">Exibe a `MethodDesc` estrutura no endereço especificado no código JIT.</span><span class="sxs-lookup"><span data-stu-id="348dc-184">Displays the `MethodDesc` structure at the specified address in JIT code.</span></span>                     |
| `histclear <arguments>`             | <span data-ttu-id="348dc-185">Libera todos os recursos usados pela família de comandos `hist*`.</span><span class="sxs-lookup"><span data-stu-id="348dc-185">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="348dc-186">Inicializa as estruturas de SOS com base no log de estresse salvo no elemento a ser depurado.</span><span class="sxs-lookup"><span data-stu-id="348dc-186">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="348dc-187">Exibe as realocações de log de estresse da coleta de lixo relacionadas ao `<arguments>` .</span><span class="sxs-lookup"><span data-stu-id="348dc-187">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="348dc-188">Exibe todas as entradas de log que fazem referência ao objeto no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="348dc-188">Displays all the log entries that reference the object at the specified address.</span></span>              |
| `histroot <arguments>`              | <span data-ttu-id="348dc-189">Exibe informações relacionadas a ambas as promoções e realocações da raiz especificada.</span><span class="sxs-lookup"><span data-stu-id="348dc-189">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="348dc-190">Exibe os módulos nativos no processo.</span><span class="sxs-lookup"><span data-stu-id="348dc-190">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="348dc-191">Exibe as `MethodTable` `EEClass` estruturas e para o `<argument>` .</span><span class="sxs-lookup"><span data-stu-id="348dc-191">Displays the `MethodTable` and `EEClass` structures for the `<argument>`.</span></span>                     |
| `pe|printexception <arguments>`     | <span data-ttu-id="348dc-192">Exibe qualquer objeto derivado da <xref:System.Exception> classe para o `<argument>` .</span><span class="sxs-lookup"><span data-stu-id="348dc-192">Displays any object derived from the <xref:System.Exception> class for the `<argument>`.</span></span>      |
| `setsymbolserver <arguments>`       | <span data-ttu-id="348dc-193">Habilita o suporte ao servidor de símbolos</span><span class="sxs-lookup"><span data-stu-id="348dc-193">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="348dc-194">Exibe as informações do SyncBlock de suporte.</span><span class="sxs-lookup"><span data-stu-id="348dc-194">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="348dc-195">Define ou exibe a ID de thread atual para os comandos SOS.</span><span class="sxs-lookup"><span data-stu-id="348dc-195">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

> [!NOTE]
> <span data-ttu-id="348dc-196">Detalhes adicionais podem ser encontrados na [extensão de depuração SOS para .net](sos-debugging-extension.md).</span><span class="sxs-lookup"><span data-stu-id="348dc-196">Additional details can be found in [SOS Debugging Extension for .NET](sos-debugging-extension.md).</span></span>

## <a name="using-dotnet-dump"></a><span data-ttu-id="348dc-197">Usando `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="348dc-197">Using `dotnet-dump`</span></span>

<span data-ttu-id="348dc-198">A primeira etapa é coletar um despejo.</span><span class="sxs-lookup"><span data-stu-id="348dc-198">The first step is to collect a dump.</span></span> <span data-ttu-id="348dc-199">Esta etapa poderá ser ignorada se um dump principal já tiver sido gerado.</span><span class="sxs-lookup"><span data-stu-id="348dc-199">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="348dc-200">O sistema operacional ou o [recurso de geração de despejo](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) interno do tempo de execução do .NET Core pode criar dumps de núcleo.</span><span class="sxs-lookup"><span data-stu-id="348dc-200">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="348dc-201">Agora, analise o dump principal com o `analyze` comando:</span><span class="sxs-lookup"><span data-stu-id="348dc-201">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="348dc-202">Essa ação abre uma sessão interativa que aceita comandos como:</span><span class="sxs-lookup"><span data-stu-id="348dc-202">This action brings up an interactive session that accepts commands like:</span></span>

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

<span data-ttu-id="348dc-203">Para ver uma exceção sem tratamento que eliminou seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="348dc-203">To see an unhandled exception that killed your app:</span></span>

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a><span data-ttu-id="348dc-204">Instruções especiais para o Docker</span><span class="sxs-lookup"><span data-stu-id="348dc-204">Special instructions for Docker</span></span>

<span data-ttu-id="348dc-205">Se você estiver executando sob o Docker, a coleta de despejo exigirá `SYS_PTRACE` recursos ( `--cap-add=SYS_PTRACE` ou `--privileged` ).</span><span class="sxs-lookup"><span data-stu-id="348dc-205">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="348dc-206">Em Microsoft .NET principais imagens do Docker do SDK do Linux, alguns `dotnet-dump` comandos podem gerar a seguinte exceção:</span><span class="sxs-lookup"><span data-stu-id="348dc-206">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="348dc-207">Exceção sem tratamento: System.DllNotFoundException: não é possível carregar a biblioteca compartilhada ' libdl.so ' ou uma de suas exceções de dependência.</span><span class="sxs-lookup"><span data-stu-id="348dc-207">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="348dc-208">Para contornar esse problema, instale o pacote "libc6-dev".</span><span class="sxs-lookup"><span data-stu-id="348dc-208">To work around this problem, install the "libc6-dev" package.</span></span>

## <a name="see-also"></a><span data-ttu-id="348dc-209">Veja também</span><span class="sxs-lookup"><span data-stu-id="348dc-209">See also</span></span>

- [<span data-ttu-id="348dc-210">Blog sobre coleta e análise de despejos de memória</span><span class="sxs-lookup"><span data-stu-id="348dc-210">Collecting and analyzing memory dumps blog</span></span>](https://devblogs.microsoft.com/dotnet/collecting-and-analyzing-memory-dumps/)
- [<span data-ttu-id="348dc-211">Ferramenta de análise de heap (dotNet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="348dc-211">Heap analysis tool (dotnet-gcdump)</span></span>](dotnet-gcdump.md)
