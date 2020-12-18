---
title: Aplicativo de arquivo único
description: Saiba o que é um aplicativo de arquivo único e por que você deve considerar o uso desse modelo de implantação de aplicativo.
author: lakshanf
ms.author: lakshanf
ms.date: 12/17/2020
ms.openlocfilehash: e2d2c9ed4c28d11a77e4f840602982a36cf1c80c
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678152"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="6de2a-103">Implantação de arquivo único e executável</span><span class="sxs-lookup"><span data-stu-id="6de2a-103">Single file deployment and executable</span></span>

<span data-ttu-id="6de2a-104">Agrupar todos os arquivos dependentes do aplicativo em um único binário fornece a um desenvolvedor de aplicativos a opção atrativa para implantar e distribuir o aplicativo como um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="6de2a-105">Esse modelo de implantação está disponível desde o .NET Core 3,0 e foi aprimorado no .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="6de2a-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="6de2a-106">Anteriormente no .NET Core 3,0, quando um usuário executa seu aplicativo de arquivo único, o host do .NET Core primeiro extrai todos os arquivos para um diretório temporário antes de executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="6de2a-107">O .NET 5,0 melhora essa experiência executando diretamente o código sem a necessidade de extrair os arquivos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="6de2a-108">A implantação de arquivo único está disponível tanto para o [modelo de implantação dependente de estrutura](index.md#publish-framework-dependent) quanto para [aplicativos independentes](index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="6de2a-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="6de2a-109">O tamanho do único arquivo em um aplicativo independente será grande, já que incluirá o tempo de execução e as bibliotecas de estrutura.</span><span class="sxs-lookup"><span data-stu-id="6de2a-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="6de2a-110">A opção de implantação de arquivo único pode ser combinada com as opções de publicação [ReadyToRun](ready-to-run.md) e [Trim (um recurso experimental no .NET 5,0)](trim-self-contained.md) .</span><span class="sxs-lookup"><span data-stu-id="6de2a-110">The single file deployment option can be combined with [ReadyToRun](ready-to-run.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

## <a name="api-incompatibility"></a><span data-ttu-id="6de2a-111">Incompatibilidade de API</span><span class="sxs-lookup"><span data-stu-id="6de2a-111">API incompatibility</span></span>

<span data-ttu-id="6de2a-112">Algumas APIs não são compatíveis com a implantação de arquivo único e os aplicativos podem exigir modificações se usarem essas APIs.</span><span class="sxs-lookup"><span data-stu-id="6de2a-112">Some APIs are not compatible with single-file deployment and applications may require modification if they use these APIs.</span></span> <span data-ttu-id="6de2a-113">Se você usar uma estrutura ou pacote de terceiros, é possível que eles também possam usar uma dessas APIs e precisar de modificação.</span><span class="sxs-lookup"><span data-stu-id="6de2a-113">If you use a third-party framework or package, it's possible that they may also use one of these APIs and need modification.</span></span> <span data-ttu-id="6de2a-114">A causa mais comum de problemas é a dependência de caminhos de arquivo para arquivos ou DLLs fornecidos com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-114">The most common cause of problems is dependence on file paths for files or DLLs shipped with the application.</span></span>

<span data-ttu-id="6de2a-115">A tabela a seguir tem os detalhes relevantes da API da biblioteca de tempo de execução para uso de arquivo único.</span><span class="sxs-lookup"><span data-stu-id="6de2a-115">The table below has the relevant runtime library API details for single-file use.</span></span>

| <span data-ttu-id="6de2a-116">API</span><span class="sxs-lookup"><span data-stu-id="6de2a-116">API</span></span>                            | <span data-ttu-id="6de2a-117">Observação</span><span class="sxs-lookup"><span data-stu-id="6de2a-117">Note</span></span>                                                                   |
|--------------------------------|------------------------------------------------------------------------|
| `Assembly.Location`            | <span data-ttu-id="6de2a-118">Retorna uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="6de2a-118">Returns an empty string.</span></span>                                               |
| `Module.FullyQualifiedName`    | <span data-ttu-id="6de2a-119">Retorna uma cadeia de caracteres com o valor de `<Unknown>` ou gera uma exceção.</span><span class="sxs-lookup"><span data-stu-id="6de2a-119">Returns a string with the value of `<Unknown>` or throws an exception.</span></span> |
| `Module.Name`                  | <span data-ttu-id="6de2a-120">Retorna uma cadeia de caracteres com o valor de `<Unknown>` .</span><span class="sxs-lookup"><span data-stu-id="6de2a-120">Returns a string with the value of `<Unknown>`.</span></span>                        |
| `Assembly.GetFile`             | <span data-ttu-id="6de2a-121">Gera <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="6de2a-121">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.GetFiles`            | <span data-ttu-id="6de2a-122">Gera <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="6de2a-122">Throws <xref:System.IO.IOException>.</span></span>                                   |
| `Assembly.CodeBase`            | <span data-ttu-id="6de2a-123">Gera <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="6de2a-123">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `Assembly.EscapedCodeBase`     | <span data-ttu-id="6de2a-124">Gera <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="6de2a-124">Throws <xref:System.PlatformNotSupportedException>.</span></span>                    |
| `AssemblyName.CodeBase`        | <span data-ttu-id="6de2a-125">Retorna `null`.</span><span class="sxs-lookup"><span data-stu-id="6de2a-125">Returns `null`.</span></span>                                                        |
| `AssemblyName.EscapedCodeBase` | <span data-ttu-id="6de2a-126">Retorna `null`.</span><span class="sxs-lookup"><span data-stu-id="6de2a-126">Returns `null`.</span></span>                                                        |

<span data-ttu-id="6de2a-127">Temos algumas recomendações para corrigir cenários comuns:</span><span class="sxs-lookup"><span data-stu-id="6de2a-127">We have some recommendations for fixing common scenarios:</span></span>

* <span data-ttu-id="6de2a-128">Para acessar arquivos ao lado do executável, use <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6de2a-128">To access files next to the executable, use <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="6de2a-129">Para localizar o nome de arquivo do executável, use o primeiro elemento de <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6de2a-129">To find the file name of the executable, use the first element of <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="6de2a-130">Para evitar inteiramente o envio de arquivos soltos, considere o uso de [recursos incorporados](../../framework/resources/creating-resource-files-for-desktop-apps.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-130">To avoid shipping loose files entirely, consider using [embedded resources](../../framework/resources/creating-resource-files-for-desktop-apps.md).</span></span>

## <a name="attaching-a-debugger"></a><span data-ttu-id="6de2a-131">Anexando um depurador</span><span class="sxs-lookup"><span data-stu-id="6de2a-131">Attaching a debugger</span></span>

<span data-ttu-id="6de2a-132">No Linux, o único depurador que pode ser anexado a processos de arquivo único independentes ou despejos de memória de depuração é [SOS com LLDB](../diagnostics/dotnet-sos.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-132">On Linux, the only debugger which can attach to self-contained single-file processes or debug crash dumps is [SOS with LLDB](../diagnostics/dotnet-sos.md).</span></span>

<span data-ttu-id="6de2a-133">No Windows e no Mac, o Visual Studio e o VS Code podem ser usados para depurar despejos de memória.</span><span class="sxs-lookup"><span data-stu-id="6de2a-133">On Windows and Mac, Visual Studio and VS Code can be used to debug crash dumps.</span></span> <span data-ttu-id="6de2a-134">Anexar a um executável de arquivo único autônomo em execução requer um arquivo extra: _MSCorDbi. { dll, portanto}_.</span><span class="sxs-lookup"><span data-stu-id="6de2a-134">Attaching to a running self-contained single-file executable requires an extra file: _mscordbi.{dll,so}_.</span></span>

<span data-ttu-id="6de2a-135">Sem esse arquivo, o Visual Studio pode produzir o erro "não é possível anexar ao processo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-135">Without this file Visual Studio may produce the error "Unable to attach to the process.</span></span> <span data-ttu-id="6de2a-136">Um componente de depuração não está instalado. "</span><span class="sxs-lookup"><span data-stu-id="6de2a-136">A debug component is not installed."</span></span> <span data-ttu-id="6de2a-137">e VS Code podem produzir o erro "falha ao anexar ao processo: erro desconhecido: 0x80131c3c."</span><span class="sxs-lookup"><span data-stu-id="6de2a-137">and VS Code may produce the error "Failed to attach to process: Unknown Error: 0x80131c3c."</span></span>

<span data-ttu-id="6de2a-138">Para corrigir esses erros, o _MSCorDbi_ precisa ser copiado ao lado do executável.</span><span class="sxs-lookup"><span data-stu-id="6de2a-138">To fix these errors, _mscordbi_ needs to be copied next to the executable.</span></span> <span data-ttu-id="6de2a-139">o _MSCorDbi_ é `publish` Ed por padrão no subdiretório com a ID de tempo de execução do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-139">_mscordbi_ is `publish`ed by default in the subdirectory with the application's runtime ID.</span></span> <span data-ttu-id="6de2a-140">Portanto, por exemplo, se uma delas fosse publicar um executável de arquivo único independente usando a `dotnet` CLI para Windows usando os parâmetros `-r win-x64` , o executável seria colocado em _bin/Debug/NET 5.0/Win-x64/Publish_.</span><span class="sxs-lookup"><span data-stu-id="6de2a-140">So, for example, if one were to publish a self-contained single-file executable using the `dotnet` CLI for Windows using the parameters `-r win-x64`, the executable would be placed in _bin/Debug/net5.0/win-x64/publish_.</span></span> <span data-ttu-id="6de2a-141">Uma cópia de _mscordbi.dll_ estaria presente em _bin/Debug/NET 5.0/Win-x64_.</span><span class="sxs-lookup"><span data-stu-id="6de2a-141">A copy of _mscordbi.dll_ would be present in _bin/Debug/net5.0/win-x64_.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="6de2a-142">Outras considerações</span><span class="sxs-lookup"><span data-stu-id="6de2a-142">Other considerations</span></span>

<span data-ttu-id="6de2a-143">Por padrão, o arquivo único não agrupa bibliotecas nativas.</span><span class="sxs-lookup"><span data-stu-id="6de2a-143">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="6de2a-144">No Linux, vinculamos o tempo de execução ao pacote e somente as bibliotecas nativas do aplicativo são implantadas no mesmo diretório que o aplicativo de arquivo único.</span><span class="sxs-lookup"><span data-stu-id="6de2a-144">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="6de2a-145">No Windows, previnculo apenas o código de hospedagem e as bibliotecas nativas de tempo de execução e aplicativo são implantadas no mesmo diretório que o aplicativo de arquivo único.</span><span class="sxs-lookup"><span data-stu-id="6de2a-145">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="6de2a-146">Isso é para garantir uma boa experiência de depuração, que exige que os arquivos nativos sejam excluídos do único arquivo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-146">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="6de2a-147">Há uma opção para definir um sinalizador, `IncludeNativeLibrariesForSelfExtract` , para incluir bibliotecas nativas no único pacote de arquivo, mas esses arquivos serão extraídos para um diretório temporário no computador cliente quando o aplicativo de arquivo único for executado.</span><span class="sxs-lookup"><span data-stu-id="6de2a-147">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

<span data-ttu-id="6de2a-148">O aplicativo de arquivo único terá todos os arquivos PDB relacionados juntamente com ele e não será agrupado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6de2a-148">Single-file application will have all related PDB files alongside it and will not be bundled by default.</span></span> <span data-ttu-id="6de2a-149">Se você quiser incluir PDBs dentro do assembly para projetos que você criar, defina o `DebugType` como `embedded` conforme descrito [abaixo](#include-pdb-files-inside-the-bundle) em detalhes.</span><span class="sxs-lookup"><span data-stu-id="6de2a-149">If you want to include PDBs inside the assembly for projects you build, set the `DebugType` to `embedded` as described [below](#include-pdb-files-inside-the-bundle) in detail.</span></span>

<span data-ttu-id="6de2a-150">Os componentes C++ gerenciados não são adequados para implantação de arquivo único e recomendamos que você escreva aplicativos em C# ou em outra linguagem C++ não gerenciada para que seja compatível com arquivo único.</span><span class="sxs-lookup"><span data-stu-id="6de2a-150">Managed C++ components aren't well suited for single-file deployment and we recommend that you write applications in C# or another non-managed C++ language to be single-file compatible.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="6de2a-151">Excluir arquivos de serem inseridos</span><span class="sxs-lookup"><span data-stu-id="6de2a-151">Exclude files from being embedded</span></span>

<span data-ttu-id="6de2a-152">Determinados arquivos podem ser explicitamente excluídos de serem inseridos no arquivo único definindo os seguintes metadados:</span><span class="sxs-lookup"><span data-stu-id="6de2a-152">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="6de2a-153">Por exemplo, para posicionar alguns arquivos no diretório de publicação, mas não agrupá-los no arquivo único:</span><span class="sxs-lookup"><span data-stu-id="6de2a-153">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="include-pdb-files-inside-the-bundle"></a><span data-ttu-id="6de2a-154">Incluir arquivos PDB dentro do pacote</span><span class="sxs-lookup"><span data-stu-id="6de2a-154">Include PDB files inside the bundle</span></span>

<span data-ttu-id="6de2a-155">O arquivo PDB de um assembly pode ser inserido no próprio assembly (o `.dll` ) usando a configuração abaixo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-155">The PDB file for an assembly can be embedded into the assembly itself (the `.dll`) using the setting below.</span></span> <span data-ttu-id="6de2a-156">Como os símbolos fazem parte do assembly, eles também serão parte do aplicativo de arquivo único:</span><span class="sxs-lookup"><span data-stu-id="6de2a-156">Since the symbols are part of the assembly, they will be part of the single-file application as well:</span></span>

```xml
<DebugType>embedded</DebugType>
```

<span data-ttu-id="6de2a-157">Por exemplo, adicione a seguinte propriedade ao arquivo de projeto de um assembly para inserir o arquivo PDB nesse assembly:</span><span class="sxs-lookup"><span data-stu-id="6de2a-157">For example, add the following property to the project file of an assembly to embed the PDB file to that assembly:</span></span>

```xml
<PropertyGroup>
  <DebugType>embedded</DebugType>
</PropertyGroup>
```

## <a name="publish-a-single-file-app---sample-project-file"></a><span data-ttu-id="6de2a-158">Publicar um aplicativo de arquivo único-arquivo de projeto de exemplo</span><span class="sxs-lookup"><span data-stu-id="6de2a-158">Publish a single file app - sample project file</span></span>

<span data-ttu-id="6de2a-159">Aqui está um arquivo de projeto de exemplo que especifica a publicação de arquivo único:</span><span class="sxs-lookup"><span data-stu-id="6de2a-159">Here's a sample project file that specifies single-file publishing:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <PublishSingleFile>true</PublishSingleFile>
    <SelfContained>true</SelfContained>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <PublishReadyToRun>true</PublishReadyToRun>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="6de2a-160">Essas propriedades têm as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="6de2a-160">These properties have the following functions:</span></span>

* <span data-ttu-id="6de2a-161">`PublishSingleFile` – Habilita a publicação de arquivo único.</span><span class="sxs-lookup"><span data-stu-id="6de2a-161">`PublishSingleFile` - Enables single-file publishing.</span></span>
* <span data-ttu-id="6de2a-162">`SelfContained` -Determina se o aplicativo será independente ou dependente de estrutura.</span><span class="sxs-lookup"><span data-stu-id="6de2a-162">`SelfContained` - Determines whether the app will be self-contained or framework-dependent.</span></span>
* <span data-ttu-id="6de2a-163">`RuntimeIdentifier` -Especifica o [sistema operacional e o tipo de CPU](../rid-catalog.md) que você está direcionando.</span><span class="sxs-lookup"><span data-stu-id="6de2a-163">`RuntimeIdentifier` - Specifies the [OS and CPU type](../rid-catalog.md) you are targeting.</span></span>
* <span data-ttu-id="6de2a-164">`PublishTrimmed` – Habilita o uso de [corte de assembly](trim-self-contained.md), que tem suporte apenas para aplicativos independentes.</span><span class="sxs-lookup"><span data-stu-id="6de2a-164">`PublishTrimmed` - Enables use of [assembly trimming](trim-self-contained.md), which is only supported for self-contained apps.</span></span>
* <span data-ttu-id="6de2a-165">`PublishReadyToRun` – Habilita [a compilação da AoT (antecipada de tempo)](ready-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-165">`PublishReadyToRun` - Enables [ahead-of-time (AOT) compilation](ready-to-run.md).</span></span>

<span data-ttu-id="6de2a-166">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="6de2a-166">**Notes:**</span></span>

* <span data-ttu-id="6de2a-167">OS aplicativos são específicos do sistema operacional e da arquitetura.</span><span class="sxs-lookup"><span data-stu-id="6de2a-167">Apps are OS and architecture-specific.</span></span> <span data-ttu-id="6de2a-168">Você precisa publicar para cada configuração, como Linux x64, Linux ARM64, Windows x64 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="6de2a-168">You need to publish for each configuration, such as Linux x64, Linux ARM64, Windows x64, and so forth.</span></span>
* <span data-ttu-id="6de2a-169">Arquivos de configuração, como *\*.runtimeconfig.jsno*, são incluídos no único arquivo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-169">Configuration files, such as *\*.runtimeconfig.json*, are included in the single file.</span></span> <span data-ttu-id="6de2a-170">Se um arquivo de configuração adicional for necessário, você poderá colocá-lo ao lado do único arquivo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-170">If an additional configuration file is needed, you can place it beside the single file.</span></span>

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="6de2a-171">Publicar um aplicativo de arquivo único-CLI</span><span class="sxs-lookup"><span data-stu-id="6de2a-171">Publish a single file app - CLI</span></span>

<span data-ttu-id="6de2a-172">Publicar um aplicativo de arquivo único usando o comando [dotnet Publish](../tools/dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="6de2a-172">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="6de2a-173">Ao publicar seu aplicativo, defina as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="6de2a-173">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="6de2a-174">Publicar para um tempo de execução específico: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="6de2a-174">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="6de2a-175">Publicar como um arquivo único: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="6de2a-175">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="6de2a-176">O exemplo a seguir publica um aplicativo para o Windows como um aplicativo de arquivo único independente.</span><span class="sxs-lookup"><span data-stu-id="6de2a-176">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="6de2a-177">O exemplo a seguir publica um aplicativo para Linux como um aplicativo de arquivo único dependente de estrutura.</span><span class="sxs-lookup"><span data-stu-id="6de2a-177">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="6de2a-178">Para obter mais informações, consulte [publicar aplicativos .NET Core com CLI do .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-178">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="6de2a-179">Publicar um único aplicativo de arquivo-Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6de2a-179">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="6de2a-180">O Visual Studio cria perfis de publicação reutilizáveis que controlam como seu aplicativo é publicado.</span><span class="sxs-lookup"><span data-stu-id="6de2a-180">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="6de2a-181">No painel **Gerenciador de soluções** , clique com o botão direito do mouse no projeto que você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="6de2a-181">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="6de2a-182">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6de2a-182">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Gerenciador de Soluções com um menu de clique com o botão direito do mouse, realçando a opção publicar.":::

    <span data-ttu-id="6de2a-184">Se você ainda não tiver um perfil de publicação, siga as instruções para criar um e escolha o tipo de destino da **pasta** .</span><span class="sxs-lookup"><span data-stu-id="6de2a-184">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="6de2a-185">Escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6de2a-185">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Perfil de publicação do Visual Studio com o botão Editar.":::

01. <span data-ttu-id="6de2a-187">Na caixa de diálogo **configurações de perfil** , defina as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6de2a-187">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="6de2a-188">Defina o **modo de implantação** **como autônomo**.</span><span class="sxs-lookup"><span data-stu-id="6de2a-188">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="6de2a-189">Defina o **tempo de execução de destino** para a plataforma na qual você deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="6de2a-189">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="6de2a-190">Selecione **produzir arquivo único**.</span><span class="sxs-lookup"><span data-stu-id="6de2a-190">Select **Produce single file**.</span></span>

    <span data-ttu-id="6de2a-191">Escolha **salvar** para salvar as configurações e retornar para a caixa de diálogo de **publicação** .</span><span class="sxs-lookup"><span data-stu-id="6de2a-191">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Caixa de diálogo Configurações de perfil com modo de implantação, tempo de execução de destino e opções de arquivo único realçadas.":::

01. <span data-ttu-id="6de2a-193">Escolha **publicar** para publicar seu aplicativo como um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-193">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="6de2a-194">Para obter mais informações, consulte [publicar aplicativos .NET Core com o Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-194">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="6de2a-195">Publicar um único aplicativo de arquivo-Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="6de2a-195">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="6de2a-196">Visual Studio para Mac não fornece opções para publicar seu aplicativo como um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="6de2a-196">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="6de2a-197">Você precisará publicar manualmente seguindo as instruções da seção [publicar um único arquivo app-CLI](#publish-a-single-file-app---cli) .</span><span class="sxs-lookup"><span data-stu-id="6de2a-197">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="6de2a-198">Para obter mais informações, consulte [publicar aplicativos .NET Core com CLI do .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-198">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6de2a-199">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6de2a-199">See also</span></span>

- <span data-ttu-id="6de2a-200">[Implantação de aplicativo .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-200">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="6de2a-201">[Publicar aplicativos .NET Core com CLI do .NET Core](deploy-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-201">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="6de2a-202">[Publicar aplicativos .NET Core com o Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-202">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="6de2a-203">[ `dotnet publish` comando](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="6de2a-203">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
