---
title: Depurar despejos do Linux
description: Neste artigo, você aprenderá a coletar e analisar despejos de ambientes Linux.
ms.date: 08/27/2020
ms.openlocfilehash: e6f2eea3af718853ad7365a5209b397a66035dde
ms.sourcegitcommit: 35ca2255c6c86968eaef9e3a251c9739ce8e4288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/23/2020
ms.locfileid: "97753595"
---
# <a name="debug-linux-dumps"></a><span data-ttu-id="3c34d-103">Depurar despejos do Linux</span><span class="sxs-lookup"><span data-stu-id="3c34d-103">Debug Linux dumps</span></span>

<span data-ttu-id="3c34d-104">**Este artigo aplica-se a: ✔️** SDK do .net Core 3,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="3c34d-104">**This article applies to: ✔️** .NET Core 3.0 SDK and later versions</span></span>

## <a name="collect-dumps-on-linux"></a><span data-ttu-id="3c34d-105">Coletar despejos no Linux</span><span class="sxs-lookup"><span data-stu-id="3c34d-105">Collect dumps on Linux</span></span>

<span data-ttu-id="3c34d-106">As duas maneiras recomendadas de coletar despejos no Linux são:</span><span class="sxs-lookup"><span data-stu-id="3c34d-106">The two recommended ways of collecting dumps on Linux are:</span></span>

* <span data-ttu-id="3c34d-107">[`dotnet-dump`](dotnet-dump.md) Ferramenta CLI</span><span class="sxs-lookup"><span data-stu-id="3c34d-107">[`dotnet-dump`](dotnet-dump.md) CLI tool</span></span>
* <span data-ttu-id="3c34d-108">[Variáveis de ambiente](dumps.md#collecting-dumps-on-crash) que coletam despejos em falhas</span><span class="sxs-lookup"><span data-stu-id="3c34d-108">[Environment variables](dumps.md#collecting-dumps-on-crash) that collect dumps on crashes</span></span>

### <a name="managed-dumps-with-dotnet-dump"></a><span data-ttu-id="3c34d-109">Despejos gerenciados com `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="3c34d-109">Managed dumps with `dotnet-dump`</span></span>

<span data-ttu-id="3c34d-110">A [`dotnet-dump`](dotnet-dump.md) ferramenta é simples de usar e não tem uma dependência em nenhum depurador nativo.</span><span class="sxs-lookup"><span data-stu-id="3c34d-110">The [`dotnet-dump`](dotnet-dump.md) tool is simple to use, and does not have a dependency on any native debuggers.</span></span> <span data-ttu-id="3c34d-111">`dotnet-dump` funciona em uma ampla variedade de plataformas Linux (como Alpine ou ARM32/ARM64), em que as ferramentas de depuração tradicionais podem não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3c34d-111">`dotnet-dump` works on a wide variety of Linux platforms (like Alpine or ARM32/ARM64) where traditional debugging tools may not be available.</span></span> <span data-ttu-id="3c34d-112">No entanto, o `dotnet-dump` só captura o estado gerenciado para que ele não possa ser usado para problemas de depuração no código nativo.</span><span class="sxs-lookup"><span data-stu-id="3c34d-112">However, `dotnet-dump` only captures managed state so it can't be used for debugging issues in native code.</span></span> <span data-ttu-id="3c34d-113">Os despejos coletados pelo `dotnet-dump` são analisados em um ambiente com o mesmo sistema operacional e arquitetura em que o despejo foi criado.</span><span class="sxs-lookup"><span data-stu-id="3c34d-113">Dumps collected by `dotnet-dump` are analyzed in an environment with the same OS and architecture the dump was created on.</span></span> <span data-ttu-id="3c34d-114">A [`dotnet-gcdump`](dotnet-gcdump.md) ferramenta pode ser usada como uma alternativa que captura apenas informações de heap do GC, mas produz despejos que podem ser analisados no Windows.</span><span class="sxs-lookup"><span data-stu-id="3c34d-114">The [`dotnet-gcdump`](dotnet-gcdump.md) tool can be used as an alternative that only captures GC heap information but produces dumps that can be analyzed on Windows.</span></span>

### <a name="core-dumps-with-createdump"></a><span data-ttu-id="3c34d-115">Dumps principais com `createdump`</span><span class="sxs-lookup"><span data-stu-id="3c34d-115">Core dumps with `createdump`</span></span>

<span data-ttu-id="3c34d-116">Como alternativa ao `dotnet-dump` , que cria despejos somente gerenciados, [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) é a ferramenta recomendada para criar dumps de núcleo no Linux contendo informações nativas e gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="3c34d-116">As an alternative to `dotnet-dump`, which creates managed-only dumps, [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) is the recommended tool for creating core dumps on Linux containing both native and managed information.</span></span> <span data-ttu-id="3c34d-117">Outras ferramentas como o gdb ou o gcore também podem ser usadas para criar dumps principais, mas podem perder o estado necessário para a depuração gerenciada, resultando em nomes de função ou tipo "desconhecido" durante a análise.</span><span class="sxs-lookup"><span data-stu-id="3c34d-117">Other tools like gdb or gcore can also be used to create core dumps but may miss state needed for managed debugging, resulting in "UNKNOWN" type or function names during analysis.</span></span>

<span data-ttu-id="3c34d-118">A `createdump` ferramenta é instalada com o tempo de execução do .NET Core e pode ser encontrada ao lado de libcoreclr.so (normalmente em "/usr/share/dotnet/Shared/Microsoft.NETCore.app/[Version]").</span><span class="sxs-lookup"><span data-stu-id="3c34d-118">The `createdump` tool is installed with the .NET Core runtime and can be found next to libcoreclr.so (typically in "/usr/share/dotnet/shared/Microsoft.NETCore.App/[version]").</span></span> <span data-ttu-id="3c34d-119">A ferramenta usa uma ID de processo para coletar um despejo de como seu argumento principal e também pode usar parâmetros opcionais que especificam o tipo de despejo a ser coletado (um minidespejo com heap é o padrão).</span><span class="sxs-lookup"><span data-stu-id="3c34d-119">The tool takes a process ID to collect a dump from as its primary argument and can also take optional parameters specifying what kind of dump to collect (a minidump with heap is the default).</span></span> <span data-ttu-id="3c34d-120">As opções incluem:</span><span class="sxs-lookup"><span data-stu-id="3c34d-120">Options include:</span></span>

- **`<input-filename>`**

  <span data-ttu-id="3c34d-121">Arquivo de rastreamento de entrada a ser convertido.</span><span class="sxs-lookup"><span data-stu-id="3c34d-121">Input trace file to be converted.</span></span> <span data-ttu-id="3c34d-122">O padrão é *trace. NetTrace*.</span><span class="sxs-lookup"><span data-stu-id="3c34d-122">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="3c34d-123">Opções</span><span class="sxs-lookup"><span data-stu-id="3c34d-123">Options</span></span>

- **`-f|--name <output-filename>`**

  <span data-ttu-id="3c34d-124">O arquivo no qual gravar o despejo.</span><span class="sxs-lookup"><span data-stu-id="3c34d-124">The file to write the dump to.</span></span> <span data-ttu-id="3c34d-125">O padrão é '/tmp/coredump.%p ', em que% p é a ID de processo do processo de destino.</span><span class="sxs-lookup"><span data-stu-id="3c34d-125">Default is '/tmp/coredump.%p' where %p is the process ID of the target process.</span></span>

- **`-n|--normal`**

  <span data-ttu-id="3c34d-126">Crie um minidespejo.</span><span class="sxs-lookup"><span data-stu-id="3c34d-126">Create a minidump.</span></span>

- **`-h|--withheap`**

  <span data-ttu-id="3c34d-127">Crie um minidespejo com heap (padrão).</span><span class="sxs-lookup"><span data-stu-id="3c34d-127">Create a minidump with heap (default).</span></span>

- **`-t|--triage`**

  <span data-ttu-id="3c34d-128">Criar um minidespejo de triagem.</span><span class="sxs-lookup"><span data-stu-id="3c34d-128">Create a triage minidump.</span></span>

- **`-u|--full`**

  <span data-ttu-id="3c34d-129">Crie um dump de núcleo completo.</span><span class="sxs-lookup"><span data-stu-id="3c34d-129">Create a full core dump.</span></span>

- **`-d|--diag`**

  <span data-ttu-id="3c34d-130">Habilitar mensagens de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="3c34d-130">Enable diagnostic messages.</span></span>

<span data-ttu-id="3c34d-131">A coleta de despejos de núcleo requer o `SYS_PTRACE` recurso ou pode `createdump` ser executada com sudo ou su.</span><span class="sxs-lookup"><span data-stu-id="3c34d-131">Collecting core dumps requires either the `SYS_PTRACE` capability or that `createdump` be run with sudo or su.</span></span>

## <a name="analyze-dumps-on-linux"></a><span data-ttu-id="3c34d-132">Analisar despejos no Linux</span><span class="sxs-lookup"><span data-stu-id="3c34d-132">Analyze dumps on Linux</span></span>

<span data-ttu-id="3c34d-133">Ambos os despejos gerenciados coletados com `dotnet-dump` o e os dumps principais coletados com `createdump` o podem ser analisados com a `dotnet-dump` ferramenta usando o `dotnet-dump analyze` comando.</span><span class="sxs-lookup"><span data-stu-id="3c34d-133">Both managed dumps collected with `dotnet-dump` and core dumps collected with `createdump` can be analyzed with the `dotnet-dump` tool using the `dotnet-dump analyze` command.</span></span> <span data-ttu-id="3c34d-134">O `dotnet dump` requer que o ambiente que analisa o despejo tenha o mesmo sistema operacional e arquitetura que o ambiente no qual o despejo foi capturado.</span><span class="sxs-lookup"><span data-stu-id="3c34d-134">The `dotnet dump` requires that the environment analyzing the dump has the same OS and architecture as the environment the dump was captured in.</span></span>

<span data-ttu-id="3c34d-135">Como alternativa, o [LLDB](https://lldb.llvm.org/) pode ser usado para analisar os dumps principais no Linux, que permite a análise de quadros gerenciados e nativos.</span><span class="sxs-lookup"><span data-stu-id="3c34d-135">Alternatively, [LLDB](https://lldb.llvm.org/) can be used to analyze core dumps on Linux, which allows analysis of both managed and native frames.</span></span> <span data-ttu-id="3c34d-136">LLDB usa a extensão SOS para depurar código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="3c34d-136">LLDB uses the SOS extension to debug managed code.</span></span> <span data-ttu-id="3c34d-137">A [`dotnet-sos`](dotnet-sos.md) ferramenta CLI pode ser usada para instalar o SOS, que tem [muitos comandos úteis](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) para depurar código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="3c34d-137">The [`dotnet-sos`](dotnet-sos.md) CLI tool can be used to install SOS, which has [many useful commands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) for debugging managed code.</span></span> <span data-ttu-id="3c34d-138">Para analisar os despejos do .NET Core, o LLDB e o SOS exigem os seguintes binários do .NET Core do ambiente no qual o despejo foi criado:</span><span class="sxs-lookup"><span data-stu-id="3c34d-138">In order to analyze .NET Core dumps, LLDB and SOS require the following .NET Core binaries from the environment the dump was created in:</span></span>

1. <span data-ttu-id="3c34d-139">libmscordaccore.so</span><span class="sxs-lookup"><span data-stu-id="3c34d-139">libmscordaccore.so</span></span>
2. <span data-ttu-id="3c34d-140">libcoreclr.so</span><span class="sxs-lookup"><span data-stu-id="3c34d-140">libcoreclr.so</span></span>
3. <span data-ttu-id="3c34d-141">dotNet (o host usado para iniciar o aplicativo)</span><span class="sxs-lookup"><span data-stu-id="3c34d-141">dotnet (the host used to launch the app)</span></span>

<span data-ttu-id="3c34d-142">Na maioria dos casos, esses binários podem ser baixados usando a [`dotnet-symbol`](dotnet-symbol.md) ferramenta.</span><span class="sxs-lookup"><span data-stu-id="3c34d-142">In most cases, these binaries can be downloaded using the [`dotnet-symbol`](dotnet-symbol.md) tool.</span></span> <span data-ttu-id="3c34d-143">Se os binários necessários não puderem ser baixados com `dotnet-symbol` (por exemplo, se uma versão particular do .NET Core criada a partir da origem estiver em uso), poderá ser necessário copiar os arquivos listados acima do ambiente no qual o despejo foi criado.</span><span class="sxs-lookup"><span data-stu-id="3c34d-143">If the necessary binaries can't be downloaded with `dotnet-symbol` (for example, if a private version of .NET Core built from source was in use), it may be necessary to copy the files listed above from the environment the dump was created in.</span></span> <span data-ttu-id="3c34d-144">Se os arquivos não estiverem localizados ao lado do arquivo de despejo, você poderá usar o comando LLDB/SOS `setclrpath <path>` para definir o caminho do qual eles devem ser carregados e `setsymbolserver -directory <path>` definir o caminho para procurar arquivos de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3c34d-144">If the files aren't located next to the dump file, you can use the LLDB/SOS command `setclrpath <path>` to set the path they should be loaded from and `setsymbolserver -directory <path>` to set the path to look in for symbol files.</span></span>

<span data-ttu-id="3c34d-145">Depois que os arquivos necessários estiverem disponíveis, o despejo poderá ser carregado em LLDB especificando o host dotnet como o executável a ser depurado:</span><span class="sxs-lookup"><span data-stu-id="3c34d-145">Once the necessary files are available, the dump can be loaded in LLDB by specifying the dotnet host as the executable to debug:</span></span>

```console
lldb --core <dump-file> <host-program>
```

<span data-ttu-id="3c34d-146">Na linha de comando acima, `<dump-file>` é o caminho do despejo a ser analisado e `<host-program>` é o programa nativo que iniciou o aplicativo .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3c34d-146">In the above command line, `<dump-file>` is the path of the dump to analyze and `<host-program>` is the native program that started the .NET Core application.</span></span> <span data-ttu-id="3c34d-147">Normalmente, esse é o `dotnet` binário, a menos que o aplicativo seja independente; nesse caso, ele é o nome do aplicativo sem a extensão de dll.</span><span class="sxs-lookup"><span data-stu-id="3c34d-147">This is typically the `dotnet` binary unless the app is self-contained, in which case it is the name of the application without the dll extension.</span></span>

<span data-ttu-id="3c34d-148">Depois que o LLDB é iniciado, pode ser necessário usar o `setsymbolserver` comando para apontar para o local correto do símbolo ( `setsymbolserver -ms` para usar o servidor de símbolos da Microsoft ou `setsymbolserver -directory <path>` para especificar um caminho local).</span><span class="sxs-lookup"><span data-stu-id="3c34d-148">Once LLDB starts, it may be necessary to use the `setsymbolserver` command to point at the correct symbol location (`setsymbolserver -ms` to use Microsoft's symbol server or `setsymbolserver -directory <path>` to specify a local path).</span></span> <span data-ttu-id="3c34d-149">Os símbolos nativos podem ser carregados executando `loadsymbols` .</span><span class="sxs-lookup"><span data-stu-id="3c34d-149">Native symbols can be loaded by running `loadsymbols`.</span></span> <span data-ttu-id="3c34d-150">Neste ponto, os [comandos do SOS](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) podem ser usados para analisar o despejo.</span><span class="sxs-lookup"><span data-stu-id="3c34d-150">At this point, [SOS commands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) can be used to analyze the dump.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c34d-151">Veja também</span><span class="sxs-lookup"><span data-stu-id="3c34d-151">See also</span></span>

- <span data-ttu-id="3c34d-152">[dotnet-SOS](dotnet-sos.md) para obter mais detalhes sobre como instalar a extensão SOS.</span><span class="sxs-lookup"><span data-stu-id="3c34d-152">[dotnet-sos](dotnet-sos.md) for more details on installing the SOS extension.</span></span>
- <span data-ttu-id="3c34d-153">[dotnet-símbolo](dotnet-symbol.md) para obter mais detalhes sobre como instalar e usar a ferramenta de download de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3c34d-153">[dotnet-symbol](dotnet-symbol.md) for more details on installing and using the symbol download tool.</span></span>
- <span data-ttu-id="3c34d-154">[Repositório de diagnóstico do .NET Core](https://github.com/dotnet/diagnostics/blob/master/documentation/) para obter mais detalhes sobre a depuração, incluindo uma FAQ útil.</span><span class="sxs-lookup"><span data-stu-id="3c34d-154">[.NET Core diagnostics repo](https://github.com/dotnet/diagnostics/blob/master/documentation/) for more details on debugging, including a useful FAQ.</span></span>
- <span data-ttu-id="3c34d-155">[Instalando o LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) para obter instruções sobre como instalar o LLDB no Linux ou no Mac.</span><span class="sxs-lookup"><span data-stu-id="3c34d-155">[Installing LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) for instructions on installing LLDB on Linux or Mac.</span></span>
