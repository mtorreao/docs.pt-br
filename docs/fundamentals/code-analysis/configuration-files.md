---
title: Arquivos de configuração para regras de análise de código
description: Saiba mais sobre arquivos de configuração diferentes para configurar regras de análise de código.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: cf9b8f4033e6774684b2b7e3b788ef3c157d95df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96585635"
---
# <a name="configuration-files-for-code-analysis-rules"></a><span data-ttu-id="1b199-103">Arquivos de configuração para regras de análise de código</span><span class="sxs-lookup"><span data-stu-id="1b199-103">Configuration files for code analysis rules</span></span>

<span data-ttu-id="1b199-104">As regras de análise de código têm várias [Opções de configuração](configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="1b199-104">Code analysis rules have various [configuration options](configuration-options.md).</span></span> <span data-ttu-id="1b199-105">Você especifica essas opções como pares de chave-valor em um dos seguintes arquivos de configuração do analisador:</span><span class="sxs-lookup"><span data-stu-id="1b199-105">You specify these options as key-value pairs in one of the following analyzer configuration files:</span></span>

- <span data-ttu-id="1b199-106">[EditorConfig](#editorconfig) arquivo: opções de configuração baseadas em arquivo ou em pasta.</span><span class="sxs-lookup"><span data-stu-id="1b199-106">[EditorConfig](#editorconfig) file: File-based or folder-based configuration options.</span></span>
- <span data-ttu-id="1b199-107">Arquivo [AnalyzerConfig global](#global-analyzerconfig) : opções de configuração no nível do projeto.</span><span class="sxs-lookup"><span data-stu-id="1b199-107">[Global AnalyzerConfig](#global-analyzerconfig) file: Project-level configuration options.</span></span>

## EditorConfig

<span data-ttu-id="1b199-108">[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) os arquivos são usados para fornecer **opções que se aplicam a arquivos ou pastas de origem específicos**.</span><span class="sxs-lookup"><span data-stu-id="1b199-108">[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) files are used to provide **options that apply to specific source files or folders**.</span></span> <span data-ttu-id="1b199-109">As opções são colocadas em cabeçalhos de seção para identificar os arquivos e pastas aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="1b199-109">Options are placed under section headers to identify the applicable files and folders.</span></span> <span data-ttu-id="1b199-110">Adicione uma entrada para cada regra que você deseja configurar e coloque-a na seção extensão de arquivo correspondente, por exemplo, `[*.cs]` .</span><span class="sxs-lookup"><span data-stu-id="1b199-110">Add an entry for each rule you want to configure, and place it under the corresponding file extension section, for example, `[*.cs]`.</span></span>

```ini
[*.cs]
<option_name> = <option_value>
```

<span data-ttu-id="1b199-111">No exemplo acima, `[*.cs]` é um cabeçalho de seção editorconfig para selecionar todos os arquivos C# com `.cs` extensão de arquivo na pasta atual, incluindo subpastas.</span><span class="sxs-lookup"><span data-stu-id="1b199-111">In the above example, `[*.cs]` is an editorconfig section header to select all C# files with `.cs` file extension within the current folder, including subfolders.</span></span> <span data-ttu-id="1b199-112">A entrada subsequente, `<option_name> = <option_value>` , é uma opção do analisador que será aplicada a todos os arquivos C#.</span><span class="sxs-lookup"><span data-stu-id="1b199-112">The subsequent entry, `<option_name> = <option_value>`, is an analyzer option that will be applied to all the C# files.</span></span>

<span data-ttu-id="1b199-113">Você pode aplicar EditorConfig convenções de arquivo a uma pasta, um projeto ou um repositório inteiro colocando o arquivo no diretório correspondente.</span><span class="sxs-lookup"><span data-stu-id="1b199-113">You can apply EditorConfig file conventions to a folder, a project, or an entire repo by placing the file in the corresponding directory.</span></span> <span data-ttu-id="1b199-114">Essas opções são aplicadas ao executar a análise no momento da compilação e enquanto você edita o código no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1b199-114">These options are applied when executing the analysis at build time and while you edit code in Visual Studio.</span></span>

<span data-ttu-id="1b199-115">Se você tiver um arquivo *. editorconfig* existente para as configurações do editor, como o tamanho do recuo ou se deseja cortar o espaço em branco à direita, você poderá posicionar as opções de configuração da análise de código no mesmo arquivo.</span><span class="sxs-lookup"><span data-stu-id="1b199-115">If you have an existing *.editorconfig* file for editor settings such as indent size or whether to trim trailing whitespace, you can place your code analysis configuration options in the same file.</span></span>

> [!TIP]
> <span data-ttu-id="1b199-116">O Visual Studio fornece um modelo de item *. editorconfig* que torna fácil adicionar um desses arquivos ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="1b199-116">Visual Studio provides an *.editorconfig* item template that makes is easy to add one of these files to your project.</span></span> <span data-ttu-id="1b199-117">Para obter mais informações, consulte [Adicionar um EditorConfig arquivo a um projeto](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).</span><span class="sxs-lookup"><span data-stu-id="1b199-117">For more information, see [Add an EditorConfig file to a project](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).</span></span>

### <a name="example"></a><span data-ttu-id="1b199-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1b199-118">Example</span></span>

<span data-ttu-id="1b199-119">A seguir, um EditorConfig arquivo de exemplo para configurar as opções e a severidade da regra:</span><span class="sxs-lookup"><span data-stu-id="1b199-119">Following is an example EditorConfig file to configure options and rule severity:</span></span>

```ini
# Remove the line below if you want to inherit .editorconfig settings from higher directories
root = true

# C# files
[*.cs]

#### Core EditorConfig Options ####

# Indentation and spacing
indent_size = 4
indent_style = space
tab_width = 4

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="global-analyzerconfig"></a><span data-ttu-id="1b199-120">AnalyzerConfig global</span><span class="sxs-lookup"><span data-stu-id="1b199-120">Global AnalyzerConfig</span></span>

<span data-ttu-id="1b199-121">A partir do SDK do .NET 5,0 (que tem suporte no Visual Studio 2019 versão 16,8 e versões posteriores), você também pode configurar opções do analisador com arquivos _AnalyzerConfig_ globais.</span><span class="sxs-lookup"><span data-stu-id="1b199-121">Starting with the .NET 5.0 SDK (which is supported in Visual Studio 2019 version 16.8 and later versions), you can also configure analyzer options with global _AnalyzerConfig_ files.</span></span> <span data-ttu-id="1b199-122">Esses arquivos são usados para fornecer **opções que se aplicam a todos os arquivos de origem em um projeto**, independentemente de seus nomes de arquivo ou caminhos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="1b199-122">These files are used to provide **options that apply to all the source files in a project**, regardless of their file names or file paths.</span></span>

<span data-ttu-id="1b199-123">Ao contrário dos [EditorConfig](#editorconfig) arquivos, os arquivos de configuração global não podem ser usados para definir as configurações de estilo do editor para ides, como recuar tamanho ou se deseja aparar o espaço em branco à direita.</span><span class="sxs-lookup"><span data-stu-id="1b199-123">Unlike [EditorConfig](#editorconfig) files, global config files can't be used to configure editor style settings for IDEs, such as indent size or whether to trim trailing whitespace.</span></span> <span data-ttu-id="1b199-124">Em vez disso, eles são projetados puramente para especificar opções de configuração do analisador de nível de projeto.</span><span class="sxs-lookup"><span data-stu-id="1b199-124">Instead, they are designed purely for specifying project-level analyzer configuration options.</span></span>

### <a name="format"></a><span data-ttu-id="1b199-125">Formatar</span><span class="sxs-lookup"><span data-stu-id="1b199-125">Format</span></span>

<span data-ttu-id="1b199-126">Ao contrário dos EditorConfig arquivos, que devem ter cabeçalhos de seção, como `[*.cs]` , para identificar os arquivos e pastas aplicáveis, os arquivos AnalyzerConfig globais não têm cabeçalhos de seção.</span><span class="sxs-lookup"><span data-stu-id="1b199-126">Unlike EditorConfig files, which must have section headers, such as `[*.cs]`, to identify the applicable files and folders, global AnalyzerConfig files don't have section headers.</span></span> <span data-ttu-id="1b199-127">Em vez disso, eles exigem uma entrada de nível superior do formulário `is_global = true` para diferenciá-los de EditorConfig arquivos regulares.</span><span class="sxs-lookup"><span data-stu-id="1b199-127">Instead, they require a top level entry of the form `is_global = true` to differentiate them from regular EditorConfig files.</span></span> <span data-ttu-id="1b199-128">Isso indica que todas as opções no arquivo se aplicam a todo o projeto.</span><span class="sxs-lookup"><span data-stu-id="1b199-128">This indicates that all the options in the file apply to the entire project.</span></span> <span data-ttu-id="1b199-129">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b199-129">For example:</span></span>

```ini
is_global = true
<option_name> = <option_value>
```

### <a name="naming"></a><span data-ttu-id="1b199-130">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1b199-130">Naming</span></span>

<span data-ttu-id="1b199-131">Ao contrário dos EditorConfig arquivos, que devem ser nomeados `.editorconfig` , os arquivos de configuração global não precisam ter um nome ou extensão específico.</span><span class="sxs-lookup"><span data-stu-id="1b199-131">Unlike EditorConfig files, which must be named `.editorconfig`, global config files do not need to have a specific name or extension.</span></span> <span data-ttu-id="1b199-132">No entanto, se você nomear esses arquivos como `.globalconfig` eles serão aplicados implicitamente a todos os projetos em C# e Visual Basic dentro da pasta atual, incluindo subpastas.</span><span class="sxs-lookup"><span data-stu-id="1b199-132">However, if you name these files as `.globalconfig` then they will be implicitly applied to all the C# and Visual Basic projects within the current folder, including subfolders.</span></span> <span data-ttu-id="1b199-133">Caso contrário, você deve adicionar explicitamente o `GlobalAnalyzerConfigFiles` item ao seu arquivo de projeto do MSBuild:</span><span class="sxs-lookup"><span data-stu-id="1b199-133">Otherwise, you must explicitly add the `GlobalAnalyzerConfigFiles` item to your MSBuild project file:</span></span>

```xml
<ItemGroup>
  <GlobalAnalyzerConfigFiles Include="<path_to_global_analyzer_config>" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="1b199-134">A entrada de nível superior `is_global = true` é necessária mesmo quando o arquivo é nomeado `.globalconfig` .</span><span class="sxs-lookup"><span data-stu-id="1b199-134">The top-level entry `is_global = true` is required even when the file is named `.globalconfig`.</span></span>

### <a name="example"></a><span data-ttu-id="1b199-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1b199-135">Example</span></span>

<span data-ttu-id="1b199-136">A seguir está um exemplo de arquivo AnalyzerConfig global para configurar as opções e a severidade da regra no nível do projeto:</span><span class="sxs-lookup"><span data-stu-id="1b199-136">Following is an example global AnalyzerConfig file to configure options and rule severity at the project level:</span></span>

```ini
# Top level entry required to mark this as a global AnalyzerConfig file
is_global = true

# NOTE: No section headers for configuration entries

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="precedence"></a><span data-ttu-id="1b199-137">Precedência</span><span class="sxs-lookup"><span data-stu-id="1b199-137">Precedence</span></span>

<span data-ttu-id="1b199-138">Os arquivos EditorConfig e os arquivos AnalyzerConfig globais especificam um par chave-valor para cada opção.</span><span class="sxs-lookup"><span data-stu-id="1b199-138">Both EditorConfig files and global AnalyzerConfig files specify a key-value pair for each option.</span></span> <span data-ttu-id="1b199-139">Os conflitos surgem quando há várias entradas com a mesma chave, mas valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="1b199-139">Conflicts arise when there are multiple entries with the same key but different values.</span></span>

### <a name="general-options"></a><span data-ttu-id="1b199-140">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="1b199-140">General options</span></span>

<span data-ttu-id="1b199-141">Quando ocorrem conflitos entre as opções, as seguintes regras de precedência são usadas para resolver os conflitos:</span><span class="sxs-lookup"><span data-stu-id="1b199-141">When conflicts arise between options, the following precedence rules are used to resolve the conflicts:</span></span>

- <span data-ttu-id="1b199-142">Entradas conflitantes no mesmo arquivo de configuração: a entrada que aparece mais adiante no arquivo vence.</span><span class="sxs-lookup"><span data-stu-id="1b199-142">Conflicting entries in the same configuration file: The entry that appears later in the file wins.</span></span> <span data-ttu-id="1b199-143">Isso é verdadeiro para entradas conflitantes dentro de um único EditorConfig arquivo e também dentro de um único arquivo AnalyzerConfig global.</span><span class="sxs-lookup"><span data-stu-id="1b199-143">This is true for conflicting entries within a single EditorConfig file and also within a single global AnalyzerConfig file.</span></span>

- <span data-ttu-id="1b199-144">Entradas conflitantes em dois EditorConfig arquivos: a entrada no EditorConfig arquivo que é mais profunda no sistema de arquivos e, portanto, tem um caminho de arquivo mais longo, o WINS.</span><span class="sxs-lookup"><span data-stu-id="1b199-144">Conflicting entries in two EditorConfig files: The entry in the EditorConfig file that's deeper in the file system, and hence has a longer file path, wins.</span></span>

- <span data-ttu-id="1b199-145">Entradas conflitantes em dois arquivos AnalyzerConfig globais: um aviso do compilador é relatado e as duas entradas são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="1b199-145">Conflicting entries in two global AnalyzerConfig files: A compiler warning is reported and both entries are ignored.</span></span>

- <span data-ttu-id="1b199-146">Entradas conflitantes em um EditorConfig arquivo e um arquivo AnalyzerConfig global: a entrada no EditorConfig arquivo vence.</span><span class="sxs-lookup"><span data-stu-id="1b199-146">Conflicting entries in an EditorConfig file and a Global AnalyzerConfig file: The entry in the EditorConfig file wins.</span></span>

### <a name="severity-options"></a><span data-ttu-id="1b199-147">Opções de severidade</span><span class="sxs-lookup"><span data-stu-id="1b199-147">Severity options</span></span>

<span data-ttu-id="1b199-148">As [regras de precedência gerais](#general-options) anteriores se aplicam a todas as opções especificadas em arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="1b199-148">The previous [general precedence rules](#general-options) apply for all options specified in configuration files.</span></span> <span data-ttu-id="1b199-149">Para opções de [configuração de gravidade](configuration-options.md#severity-level) , as seguintes regras de precedência adicionais se aplicam:</span><span class="sxs-lookup"><span data-stu-id="1b199-149">For [severity configuration](configuration-options.md#severity-level) options, the following additional precedence rules apply:</span></span>

- <span data-ttu-id="1b199-150">As opções de severidade especificadas na linha de comando como opções do compilador ( `/nowarn` ou `/warnaserror` ) sempre substituem as opções de [configuração de gravidade](configuration-options.md#severity-level) especificadas em EditorConfig e em arquivos AnalyzerConfig globais.</span><span class="sxs-lookup"><span data-stu-id="1b199-150">Severity options specified at the command line as compiler options (`/nowarn` or `/warnaserror`) always override [severity configuration](configuration-options.md#severity-level) options specified in EditorConfig and global AnalyzerConfig files.</span></span>

- <span data-ttu-id="1b199-151">As opções de severidade também podem ser especificadas com um arquivo [RuleSet](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) .</span><span class="sxs-lookup"><span data-stu-id="1b199-151">Severity options can also be specified with a [Ruleset](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) file.</span></span> <span data-ttu-id="1b199-152">No entanto, os arquivos de RuleSets são preteridos em favor EditorConfig e em arquivos AnalyzerConfig globais.</span><span class="sxs-lookup"><span data-stu-id="1b199-152">However, rulesets files are deprecated in favor of EditorConfig and global AnalyzerConfig files.</span></span> <span data-ttu-id="1b199-153">É recomendável que você [Converta arquivos RuleSet em um EditorConfig arquivo equivalente](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file).</span><span class="sxs-lookup"><span data-stu-id="1b199-153">It's recommended that you [convert ruleset files to an equivalent EditorConfig file](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file).</span></span> <span data-ttu-id="1b199-154">A precedência para entradas de severidade conflitantes de um arquivo RuleSet e de EditorConfig arquivos AnalyzerConfig global é _indefinida_.</span><span class="sxs-lookup"><span data-stu-id="1b199-154">Precedence for conflicting severity entries from a ruleset file and EditorConfig or global AnalyzerConfig files is _undefined_.</span></span>

- <span data-ttu-id="1b199-155">Para obter informações sobre regras de precedência para opções de severidade relacionadas com chaves diferentes, por exemplo, quando severidades diferentes são especificadas para uma única regra e para a categoria na qual a regra se enquadra, consulte [Opções de configuração para análise de código](configuration-options.md#precedence).</span><span class="sxs-lookup"><span data-stu-id="1b199-155">For information about precedence rules for related severity options with different keys, for example, when different severities are specified for a single rule and for the category that rule falls under, see [Configuration options for code analysis](configuration-options.md#precedence).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b199-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="1b199-156">See also</span></span>

- [<span data-ttu-id="1b199-157">EditorConfig problema no design do vs global AnalyzerConfig</span><span class="sxs-lookup"><span data-stu-id="1b199-157">EditorConfig vs global AnalyzerConfig design issue</span></span>](https://github.com/dotnet/roslyn/issues/47707)
