---
title: Configurar regras de análise de código
description: Saiba como configurar regras de análise de código em um arquivo de configuração do Analyzer.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: 4f7b392a2b066023fec75c5295bd94651654d645
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851784"
---
# <a name="configuration-options-for-code-analysis"></a><span data-ttu-id="c872e-103">Opções de configuração para análise de código</span><span class="sxs-lookup"><span data-stu-id="c872e-103">Configuration options for code analysis</span></span>

<span data-ttu-id="c872e-104">As regras de análise de código têm várias opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="c872e-104">Code analysis rules have various configuration options.</span></span> <span data-ttu-id="c872e-105">Essas opções são especificadas como pares chave-valor em um [arquivo de configuração do analisador](configuration-files.md) usando a sintaxe `<option key> = <option value>` .</span><span class="sxs-lookup"><span data-stu-id="c872e-105">These options are specified as key-value pairs in an [analyzer configuration file](configuration-files.md) using the syntax `<option key> = <option value>`.</span></span>

<span data-ttu-id="c872e-106">A opção mais comum que você configurará é a severidade de uma [regra](#severity-level).</span><span class="sxs-lookup"><span data-stu-id="c872e-106">The most common option you'll configure is a [rule's severity](#severity-level).</span></span> <span data-ttu-id="c872e-107">Você pode configurar o nível de severidade para todas as regras do analisador, incluindo [regras de qualidade de código](quality-rules/index.md) e regras de estilo de [código](style-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="c872e-107">You can configure severity level for all analyzer rules, including [code quality rules](quality-rules/index.md) and [code style rules](style-rules/index.md).</span></span> <span data-ttu-id="c872e-108">Por exemplo, para habilitar uma regra como um aviso, você pode adicionar o seguinte par chave-valor a um EditorConfig arquivo.</span><span class="sxs-lookup"><span data-stu-id="c872e-108">For example, to enable a rule as a warning, you can add the following key-value pair to an EditorConfig file.</span></span>

`dotnet_diagnostic.<rule ID>.severity = warning`

<span data-ttu-id="c872e-109">Você também pode configurar opções adicionais para personalizar o comportamento da regra:</span><span class="sxs-lookup"><span data-stu-id="c872e-109">You can also configure additional options to customize rule behavior:</span></span>

- <span data-ttu-id="c872e-110">As regras de qualidade de código têm [Opções adicionais](code-quality-rule-options.md) para configurar o comportamento, como a quais nomes de método uma regra deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="c872e-110">Code quality rules have [additional options](code-quality-rule-options.md) to configure behavior, such as which method names a rule should apply to.</span></span>
- <span data-ttu-id="c872e-111">As regras de estilo de código têm [Opções de estilo de código personalizadas](code-style-rule-options.md).</span><span class="sxs-lookup"><span data-stu-id="c872e-111">Code style rules have [custom code style options](code-style-rule-options.md).</span></span>
- <span data-ttu-id="c872e-112">As regras de analisador de terceiros podem definir suas próprias opções de configuração, com nomes de chave personalizados e formatos de valor.</span><span class="sxs-lookup"><span data-stu-id="c872e-112">Third party analyzer rules can define their own configuration options, with custom key names and value formats.</span></span>

<span data-ttu-id="c872e-113">A sintaxe para configurar a severidade de uma regra específica em um [arquivo de configuração do analisador](configuration-files.md) é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="c872e-113">The syntax for configuring a specific rule's severity in an [analyzer configuration file](configuration-files.md) is as follows:</span></span>

```ini
dotnet_diagnostic.<rule ID>.severity = <severity>
```

## <a name="general-options"></a><span data-ttu-id="c872e-114">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="c872e-114">General options</span></span>

<span data-ttu-id="c872e-115">Essas opções se aplicam à análise de código como um todo.</span><span class="sxs-lookup"><span data-stu-id="c872e-115">These options apply to code analysis as a whole.</span></span> <span data-ttu-id="c872e-116">Eles não podem ser aplicados somente a uma única regra ou conjunto de regras.</span><span class="sxs-lookup"><span data-stu-id="c872e-116">They cannot be applied only to a single rule or set of rules.</span></span>

### <a name="exclude-generated-code"></a><span data-ttu-id="c872e-117">Excluir código gerado</span><span class="sxs-lookup"><span data-stu-id="c872e-117">Exclude generated code</span></span>

<span data-ttu-id="c872e-118">Você pode configurar arquivos e pastas adicionais para serem tratados como código gerado adicionando uma `generated_code = true | false` entrada ao arquivo de [configuração](configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="c872e-118">You can configure additional files and folders to be treated as generated code by adding a `generated_code = true | false` entry to your [configuration file](configuration-files.md).</span></span> <span data-ttu-id="c872e-119">Os avisos do analisador de código .NET não são úteis em arquivos de código gerados, como arquivos gerados pelo designer, que os usuários não podem editar para corrigir quaisquer violações.</span><span class="sxs-lookup"><span data-stu-id="c872e-119">.NET code analyzer warnings aren't useful on generated code files, such as designer-generated files, which users can't edit to fix any violations.</span></span> <span data-ttu-id="c872e-120">Na maioria dos casos, os analisadores de código ignoram os arquivos de código gerados e não relatam violações nesses arquivos.</span><span class="sxs-lookup"><span data-stu-id="c872e-120">In most cases, code analyzers skip generated code files and don't report violations on these files.</span></span>

<span data-ttu-id="c872e-121">Por padrão, os arquivos com determinadas extensões de arquivo ou cabeçalhos de arquivo gerados automaticamente são tratados como arquivos de código gerados.</span><span class="sxs-lookup"><span data-stu-id="c872e-121">By default, files with certain file extensions or auto-generated file headers are treated as generated code files.</span></span> <span data-ttu-id="c872e-122">Por exemplo, um nome de arquivo que termina com `.designer.cs` ou `.generated.cs` é considerado código gerado.</span><span class="sxs-lookup"><span data-stu-id="c872e-122">For example, a file name ending with `.designer.cs` or `.generated.cs` is considered generated code.</span></span> <span data-ttu-id="c872e-123">Essa opção de configuração permite que você especifique padrões de nomenclatura adicionais.</span><span class="sxs-lookup"><span data-stu-id="c872e-123">This configuration option lets you specify additional naming patterns.</span></span>

<span data-ttu-id="c872e-124">Por exemplo, para tratar todos os arquivos cujo nome termina com `.MyGenerated.cs` o código gerado, adicione a seguinte entrada:</span><span class="sxs-lookup"><span data-stu-id="c872e-124">For example, to treat all files whose name ends with `.MyGenerated.cs` as generated code, add the following entry:</span></span>

```ini
[*.MyGenerated.cs]
generated_code = true
```

## <a name="rule-specific-options"></a><span data-ttu-id="c872e-125">Opções específicas de regra</span><span class="sxs-lookup"><span data-stu-id="c872e-125">Rule-specific options</span></span>

<span data-ttu-id="c872e-126">As opções específicas de regra podem ser aplicadas a uma única regra, a um conjunto de regras ou a todas as regras.</span><span class="sxs-lookup"><span data-stu-id="c872e-126">Rule-specific options can be applied to a single rule, a set of rules, or all rules.</span></span> <span data-ttu-id="c872e-127">As opções específicas de regra incluem:</span><span class="sxs-lookup"><span data-stu-id="c872e-127">The rule-specific options include:</span></span>

- [<span data-ttu-id="c872e-128">Nível de severidade da regra</span><span class="sxs-lookup"><span data-stu-id="c872e-128">Rule severity level</span></span>](#severity-level)
- [<span data-ttu-id="c872e-129">Opções específicas para regras de *qualidade de código*</span><span class="sxs-lookup"><span data-stu-id="c872e-129">Options specific to *code-quality* rules</span></span>](code-quality-rule-options.md)

### <a name="severity-level"></a><span data-ttu-id="c872e-130">Nível de severidade</span><span class="sxs-lookup"><span data-stu-id="c872e-130">Severity level</span></span>

<span data-ttu-id="c872e-131">A tabela a seguir mostra as diferentes severidades de regra que você pode configurar para todas as regras do analisador, incluindo a [qualidade de código](quality-rules/index.md) e as regras de [estilo de código](style-rules/index.md) .</span><span class="sxs-lookup"><span data-stu-id="c872e-131">The following table shows the different rule severities that you can configure for all analyzer rules, including [code quality](quality-rules/index.md) and [code style](style-rules/index.md) rules.</span></span>

| <span data-ttu-id="c872e-132">Severity</span><span class="sxs-lookup"><span data-stu-id="c872e-132">Severity</span></span> | <span data-ttu-id="c872e-133">Comportamento de tempo de compilação</span><span class="sxs-lookup"><span data-stu-id="c872e-133">Build-time behavior</span></span> |
|-|-|
| `error` | <span data-ttu-id="c872e-134">As violações aparecem como *erros* de compilação e causam a falha das compilações.</span><span class="sxs-lookup"><span data-stu-id="c872e-134">Violations appear as build *errors* and cause builds to fail.</span></span>|
| `warning` | <span data-ttu-id="c872e-135">As violações aparecem como *avisos* de compilação, mas não causam a falha das compilações (a menos que você tenha uma opção definida para tratar avisos como erros).</span><span class="sxs-lookup"><span data-stu-id="c872e-135">Violations appear as build *warnings* but do not cause builds to fail (unless you have an option set to treat warnings as errors).</span></span> |
| `suggestion` | <span data-ttu-id="c872e-136">As violações aparecem como *mensagens* de Build e como sugestões no IDE do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c872e-136">Violations appear as build *messages* and as suggestions in the Visual Studio IDE.</span></span> |
| `silent` | <span data-ttu-id="c872e-137">As violações não são visíveis para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c872e-137">Violations aren't visible to the user.</span></span> |
| `none` | <span data-ttu-id="c872e-138">A regra foi completamente suprimida.</span><span class="sxs-lookup"><span data-stu-id="c872e-138">Rule is suppressed completely.</span></span> |
| `default` | <span data-ttu-id="c872e-139">A severidade padrão da regra é usada.</span><span class="sxs-lookup"><span data-stu-id="c872e-139">The default severity of the rule is used.</span></span> |

> [!TIP]
> <span data-ttu-id="c872e-140">Para obter informações sobre como a superfície de severidades de regra no Visual Studio, consulte [níveis de severidade](/visualstudio/ide/editorconfig-language-conventions#severity-levels).</span><span class="sxs-lookup"><span data-stu-id="c872e-140">For information about how rule severities surface in Visual Studio, see [Severity levels](/visualstudio/ide/editorconfig-language-conventions#severity-levels).</span></span>

#### <a name="scope"></a><span data-ttu-id="c872e-141">Escopo</span><span class="sxs-lookup"><span data-stu-id="c872e-141">Scope</span></span>

<span data-ttu-id="c872e-142">Para definir a severidade da regra para uma única regra, use a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="c872e-142">To set the rule severity for a single rule, use the following syntax.</span></span>

```ini
dotnet_diagnostic.<rule ID>.severity = <severity value>
```

<span data-ttu-id="c872e-143">Para definir a severidade da regra padrão para uma categoria de regras do analisador, use a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="c872e-143">To set the default rule severity for a category of analyzer rules, use the following syntax.</span></span>

```ini
dotnet_analyzer_diagnostic.category-<rule category>.severity = <severity value>
```

<span data-ttu-id="c872e-144">Para definir a severidade da regra padrão para todas as regras do analisador, use a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="c872e-144">To set the default rule severity for all analyzer rules, use the following syntax.</span></span>

```ini
dotnet_analyzer_diagnostic.severity = <severity value>
```

#### <a name="precedence"></a><span data-ttu-id="c872e-145">Precedência</span><span class="sxs-lookup"><span data-stu-id="c872e-145">Precedence</span></span>

<span data-ttu-id="c872e-146">Se você tiver várias entradas de configuração de severidade que podem ser aplicadas à mesma ID de regra, a precedência será escolhida na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="c872e-146">If you have multiple severity configuration entries that can be applied to the same rule ID, precedence is chosen in the following order:</span></span>

- <span data-ttu-id="c872e-147">Uma entrada para uma regra individual por ID tem precedência sobre uma entrada para uma categoria.</span><span class="sxs-lookup"><span data-stu-id="c872e-147">An entry for an individual rule by ID takes precedence over an entry for a category.</span></span>
- <span data-ttu-id="c872e-148">Uma entrada para uma categoria tem precedência sobre uma entrada para todas as regras do analisador.</span><span class="sxs-lookup"><span data-stu-id="c872e-148">An entry for a category takes precedence over an entry for all analyzer rules.</span></span>

<span data-ttu-id="c872e-149">Considere o exemplo a seguir, em que [CA1822](/visualstudio/code-quality/ca1822) tem a categoria "performance":</span><span class="sxs-lookup"><span data-stu-id="c872e-149">Consider the following example, where [CA1822](/visualstudio/code-quality/ca1822) has the category "Performance":</span></span>

```ini
[*.cs]
dotnet_diagnostic.CA1822.severity = error
dotnet_analyzer_diagnostic.category-performance.severity = warning
dotnet_analyzer_diagnostic.severity = suggestion
```

<span data-ttu-id="c872e-150">No exemplo anterior, todas as três entradas de severidade são aplicáveis a CA1822.</span><span class="sxs-lookup"><span data-stu-id="c872e-150">In the preceding example, all three severity entries are applicable to CA1822.</span></span> <span data-ttu-id="c872e-151">No entanto, usando as regras de precedência especificadas, a primeira entrada baseada na ID da regra vence nas próximas entradas.</span><span class="sxs-lookup"><span data-stu-id="c872e-151">However, using the specified precedence rules, the first rule ID-based entry wins over the next entries.</span></span> <span data-ttu-id="c872e-152">Neste exemplo, o CA1822 terá uma severidade efetiva de `error` .</span><span class="sxs-lookup"><span data-stu-id="c872e-152">In this example, CA1822 will have an effective severity of `error`.</span></span> <span data-ttu-id="c872e-153">Todas as outras regras dentro da categoria "desempenho" terão uma severidade de `warning` .</span><span class="sxs-lookup"><span data-stu-id="c872e-153">All other rules within the "Performance" category will have a severity of `warning`.</span></span>

<span data-ttu-id="c872e-154">Para obter informações sobre como a precedência entre arquivos é decidida, consulte a [seção precedência do artigo arquivos de configuração](configuration-files.md#precedence).</span><span class="sxs-lookup"><span data-stu-id="c872e-154">For information about how inter-file precedence is decided, see the [Precedence section of the Configuration files article](configuration-files.md#precedence).</span></span>
