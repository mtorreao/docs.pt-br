---
title: Regras de nomenclatura de estilo de código
description: Saiba mais sobre as regras de estilo de código do .NET para elementos de código de nomenclatura.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE1006
- naming rules
helpviewer_keywords:
- IDE1006
- naming code style rules [EditorConfig]
- naming rules
- EditorConfig naming conventions
ms.openlocfilehash: 8ce209e64ee7f9f9028c221daedef8fc6a993ef7
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96585650"
---
# <a name="naming-rules"></a><span data-ttu-id="5b6a5-103">Regras de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5b6a5-103">Naming rules</span></span>

<span data-ttu-id="5b6a5-104">As regras de nomenclatura referem-se à nomenclatura de elementos de código de linguagem de programação .NET, como classes, propriedades e métodos.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-104">Naming rules concern the naming of .NET programming language code elements, such as classes, properties, and methods.</span></span> <span data-ttu-id="5b6a5-105">Por exemplo, você pode especificar que os membros públicos devem estar em letras maiúsculas ou que os campos particulares devem começar com `_` .</span><span class="sxs-lookup"><span data-stu-id="5b6a5-105">For example, you can specify that public members must be capitalized or that private fields must begin with `_`.</span></span>

<span data-ttu-id="5b6a5-106">Uma regra de nomenclatura tem três partes:</span><span class="sxs-lookup"><span data-stu-id="5b6a5-106">A naming rule has three parts:</span></span>

* <span data-ttu-id="5b6a5-107">O grupo de símbolos ao qual se aplica.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-107">The group of symbols it applies to.</span></span>
* <span data-ttu-id="5b6a5-108">O estilo de nomenclatura a ser associado à regra.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-108">The naming style to associate with the rule.</span></span>
* <span data-ttu-id="5b6a5-109">A severidade para impor a Convenção.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-109">The severity for enforcing the convention.</span></span>

<span data-ttu-id="5b6a5-110">Você define regras de nomenclatura em um arquivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-110">You define naming rules in an EditorConfig file.</span></span>

## <a name="general-syntax"></a><span data-ttu-id="5b6a5-111">Sintaxe geral</span><span class="sxs-lookup"><span data-stu-id="5b6a5-111">General syntax</span></span>

<span data-ttu-id="5b6a5-112">Para definir uma regra de nomenclatura, um grupo de símbolos ou um estilo de nomenclatura, defina uma ou mais propriedades usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5b6a5-112">To define a naming rule, symbol group, or naming style, set one or more properties using the following syntax:</span></span>

```ini
<prefix>.<title>.<propertyName> = <propertyValue>
```

<span data-ttu-id="5b6a5-113">Cada propriedade só deve ser definida uma vez, mas algumas configurações permitem vários valores separados por vírgula.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-113">Each property should only be set once, but some settings allow multiple, comma-separated values.</span></span>

<span data-ttu-id="5b6a5-114">A ordem das propriedades não é importante.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-114">The order of the properties is not important.</span></span>

### \<prefix>

<span data-ttu-id="5b6a5-115">**\<prefix>** Especifica qual tipo de elemento está sendo definido como &mdash; regra de nomenclatura, grupo de símbolos ou estilo de nomenclatura &mdash; e deve ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="5b6a5-115">**\<prefix>** specifies which kind of element is being defined&mdash;naming rule, symbol group, or naming style&mdash;and must be one of the following:</span></span>

| <span data-ttu-id="5b6a5-116">Para definir uma propriedade para</span><span class="sxs-lookup"><span data-stu-id="5b6a5-116">To set a property for</span></span> | <span data-ttu-id="5b6a5-117">Usar o prefixo</span><span class="sxs-lookup"><span data-stu-id="5b6a5-117">Use the prefix</span></span> | <span data-ttu-id="5b6a5-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5b6a5-118">Example</span></span> |
| --- | --- | -- |
| <span data-ttu-id="5b6a5-119">Regra de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5b6a5-119">Naming rule</span></span> | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| <span data-ttu-id="5b6a5-120">Grupo de símbolos</span><span class="sxs-lookup"><span data-stu-id="5b6a5-120">Symbol group</span></span> | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| <span data-ttu-id="5b6a5-121">Estilo de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5b6a5-121">Naming style</span></span> | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

<span data-ttu-id="5b6a5-122">Cada tipo de &mdash; [regra de nomenclatura](#naming-rule-properties)de definição, [grupo de símbolos](#symbol-group-properties)ou [estilo de nomenclatura](#naming-style-properties) &mdash; tem suas próprias propriedades com suporte, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-122">Each type of definition&mdash;[naming rule](#naming-rule-properties), [symbol group](#symbol-group-properties), or [naming style](#naming-style-properties)&mdash;has its own supported properties, as described in the following sections.</span></span>

### \<title>

<span data-ttu-id="5b6a5-123">**\<title>** é um nome descritivo que você escolhe que associa várias configurações de propriedade em uma única definição.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-123">**\<title>** is a descriptive name you choose that associates multiple property settings into a single definition.</span></span> <span data-ttu-id="5b6a5-124">Por exemplo, as propriedades a seguir produzem duas definições de grupo `interface` de símbolos e `types` , cada uma delas tem duas propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-124">For example, the following properties produce two symbol group definitions, `interface` and `types`, each of which has two properties set on it.</span></span>

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a><span data-ttu-id="5b6a5-125">Propriedades da regra de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5b6a5-125">Naming rule properties</span></span>

<span data-ttu-id="5b6a5-126">Todas as propriedades de regra de nomenclatura são necessárias para que uma regra entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-126">All naming rule properties are required for a rule to take effect.</span></span>

| <span data-ttu-id="5b6a5-127">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5b6a5-127">Property</span></span> | <span data-ttu-id="5b6a5-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b6a5-128">Description</span></span> |
| -- | -- |
| `symbols` | <span data-ttu-id="5b6a5-129">O título do grupo de símbolos, definindo os símbolos aos quais essa regra deve ser aplicada</span><span class="sxs-lookup"><span data-stu-id="5b6a5-129">The title of the symbol group, defining the symbols to which this rule should be applied</span></span> |
| `style` | <span data-ttu-id="5b6a5-130">O título do estilo de nomenclatura que deve ser associado a esta regra</span><span class="sxs-lookup"><span data-stu-id="5b6a5-130">The title of the naming style which should be associated with this rule</span></span> |
| `severity` |  <span data-ttu-id="5b6a5-131">Define a severidade com a qual impor a regra de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-131">Sets the severity with which to enforce the naming rule.</span></span> <span data-ttu-id="5b6a5-132">Defina o valor associado como um dos níveis de [severidade](https://docs.microsoft.com/dotnet/fundamentals/code-analysis/configuration-options#severity-level)disponíveis. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5b6a5-132">Set the associated value to one of the available [severity levels](https://docs.microsoft.com/dotnet/fundamentals/code-analysis/configuration-options#severity-level).<sup>1</sup></span></span> |

<span data-ttu-id="5b6a5-133">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="5b6a5-133">**Notes:**</span></span>

1. <span data-ttu-id="5b6a5-134">A especificação de severidade dentro de uma regra de nomenclatura só é respeitada dentro de IDEs de desenvolvimento, como o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-134">Severity specification within a naming rule is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="5b6a5-135">Essa configuração não é compreendida pelos compiladores C# ou VB, portanto não é respeitada durante a compilação.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-135">This setting is not understood by the C# or VB compilers, hence not respected during build.</span></span> <span data-ttu-id="5b6a5-136">Em vez disso, para impor regras de estilo de nomenclatura na compilação, você deve definir a gravidade usando a configuração de severidade baseada em ID de regra, conforme explicado nesta [seção](#rule-id-ide1006-naming-rule-violation).</span><span class="sxs-lookup"><span data-stu-id="5b6a5-136">Instead, to enforce naming style rules on build, you should set the severity by using the rule ID-based severity configuration as explained in [this section](#rule-id-ide1006-naming-rule-violation).</span></span> <span data-ttu-id="5b6a5-137">Para saber mais, confira este [problema do GitHub](https://github.com/dotnet/roslyn/issues/44201).</span><span class="sxs-lookup"><span data-stu-id="5b6a5-137">For more information, see this [GitHub issue](https://github.com/dotnet/roslyn/issues/44201).</span></span>

## <a name="rule-order"></a><span data-ttu-id="5b6a5-138">Ordem das regras</span><span class="sxs-lookup"><span data-stu-id="5b6a5-138">Rule order</span></span>

<span data-ttu-id="5b6a5-139">A ordem na qual as regras de nomenclatura são definidas em um arquivo EditorConfig não importa.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-139">The order in which naming rules are defined in an EditorConfig file doesn't matter.</span></span> <span data-ttu-id="5b6a5-140">As regras de nomenclatura são ordenadas automaticamente de acordo com a definição das próprias regras.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-140">The naming rules are automatically ordered according to the definition of the rules themselves.</span></span> <span data-ttu-id="5b6a5-141">A [extensão de serviço de linguagem EditorConfig](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) pode analisar um arquivo EditorConfig e casos de relatório em que a ordenação de regra no arquivo é diferente do que o compilador usará em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-141">The [EditorConfig Language Service extension](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) can analyze an EditorConfig file and report cases where the rule ordering in the file is different to what the compiler will use at run time.</span></span>

> [!NOTE]
>
> <span data-ttu-id="5b6a5-142">Se você estiver usando uma versão do Visual Studio anterior à versão 16,2 do Visual Studio 2019, as regras de nomenclatura deverão ser ordenadas da mais específica para a menos específica no arquivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-142">If you're using a version of Visual Studio earlier than Visual Studio 2019 version 16.2, naming rules should be ordered from most-specific to least-specific in the EditorConfig file.</span></span> <span data-ttu-id="5b6a5-143">A primeira regra encontrada que pode ser aplicada é a única regra que é aplicada.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-143">The first rule encountered that can be applied is the only rule that is applied.</span></span> <span data-ttu-id="5b6a5-144">No entanto, se houver várias *propriedades* de regras com o mesmo nome, a propriedade mais recente encontrada com esse nome terá precedência.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-144">However, if there are multiple rule *properties* with the same name, the most recently found property with that name takes precedence.</span></span> <span data-ttu-id="5b6a5-145">Confira mais informações em [Precedência e hierarquia de arquivos](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span><span class="sxs-lookup"><span data-stu-id="5b6a5-145">For more information, see [File hierarchy and precedence](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span></span>

## <a name="symbol-group-properties"></a><span data-ttu-id="5b6a5-146">Propriedades do grupo de símbolos</span><span class="sxs-lookup"><span data-stu-id="5b6a5-146">Symbol group properties</span></span>

<span data-ttu-id="5b6a5-147">Você pode definir as seguintes propriedades para grupos de símbolos, para limitar quais símbolos estão incluídos no grupo.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-147">You can set the following properties for symbol groups, to limit which symbols are included in the group.</span></span> <span data-ttu-id="5b6a5-148">Para especificar vários valores em uma única configuração de propriedade, separe-os com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-148">To specify multiple values in a single property setting, separate them with a comma.</span></span>

| <span data-ttu-id="5b6a5-149">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5b6a5-149">Property</span></span> | <span data-ttu-id="5b6a5-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b6a5-150">Description</span></span> | <span data-ttu-id="5b6a5-151">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="5b6a5-151">Allowed values</span></span> | <span data-ttu-id="5b6a5-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5b6a5-152">Required</span></span> |
| -- | -- | -- | -- |
| `applicable_kinds` | <span data-ttu-id="5b6a5-153">Tipos de símbolos no grupo <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5b6a5-153">Kinds of symbols in the group <sup>1</sup></span></span> | <span data-ttu-id="5b6a5-154">`*` (use este valor para especificar todos os símbolos)</span><span class="sxs-lookup"><span data-stu-id="5b6a5-154">`*` (use this value to specify all symbols)</span></span><br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | <span data-ttu-id="5b6a5-155">Sim</span><span class="sxs-lookup"><span data-stu-id="5b6a5-155">Yes</span></span> |
| `applicable_accessibilities` | <span data-ttu-id="5b6a5-156">Níveis de acessibilidade dos símbolos no grupo</span><span class="sxs-lookup"><span data-stu-id="5b6a5-156">Accessibility levels of the symbols in the group</span></span> | <span data-ttu-id="5b6a5-157">`*` (use este valor para especificar todos os níveis de acessibilidade)</span><span class="sxs-lookup"><span data-stu-id="5b6a5-157">`*` (use this value to specify all accessibility levels)</span></span><br/>`public`<br/><span data-ttu-id="5b6a5-158">`internal` ou `friend`</span><span class="sxs-lookup"><span data-stu-id="5b6a5-158">`internal` or `friend`</span></span><br/>`private`<br/>`protected`<br/><span data-ttu-id="5b6a5-159">`protected_internal` ou `protected_friend`</span><span class="sxs-lookup"><span data-stu-id="5b6a5-159">`protected_internal` or `protected_friend`</span></span><br/>`private_protected`<br/><span data-ttu-id="5b6a5-160">`local` (para símbolos definidos dentro de um método)</span><span class="sxs-lookup"><span data-stu-id="5b6a5-160">`local` (for symbols defined within a method)</span></span> | <span data-ttu-id="5b6a5-161">Sim</span><span class="sxs-lookup"><span data-stu-id="5b6a5-161">Yes</span></span> |
| `required_modifiers` | <span data-ttu-id="5b6a5-162">Corresponder apenas símbolos com _todos_ os modificadores especificados <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5b6a5-162">Only match symbols with _all_ the specified modifiers <sup>2</sup></span></span> | <span data-ttu-id="5b6a5-163">`abstract` ou `must_inherit`</span><span class="sxs-lookup"><span data-stu-id="5b6a5-163">`abstract` or `must_inherit`</span></span><br/>`async`<br/>`const`<br/>`readonly`<br/><span data-ttu-id="5b6a5-164">`static` ou `shared` <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5b6a5-164">`static` or `shared` <sup>3</sup></span></span> | <span data-ttu-id="5b6a5-165">Não</span><span class="sxs-lookup"><span data-stu-id="5b6a5-165">No</span></span> |

<span data-ttu-id="5b6a5-166">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="5b6a5-166">**Notes:**</span></span>

1. <span data-ttu-id="5b6a5-167">Atualmente, não há suporte para membros de tupla no `applicable_kinds` .</span><span class="sxs-lookup"><span data-stu-id="5b6a5-167">Tuple members aren't currently supported in `applicable_kinds`.</span></span>
2. <span data-ttu-id="5b6a5-168">O grupo de símbolos corresponde a _todos_ os modificadores na `required_modifiers` propriedade.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-168">The symbol group matches _all_ the modifiers in the `required_modifiers` property.</span></span>  <span data-ttu-id="5b6a5-169">Se você omitir essa propriedade, nenhum modificador específico será necessário para uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-169">If you omit this property, no specific modifiers are required for a match.</span></span> <span data-ttu-id="5b6a5-170">Isso significa que os modificadores de um símbolo não têm efeito sobre a opção de aplicar essa regra ou não.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-170">This means a symbol's modifiers have no effect on whether or not this rule is applied.</span></span>
3. <span data-ttu-id="5b6a5-171">Se o grupo tiver `static` ou `shared` na `required_modifiers` propriedade, o grupo também incluirá `const` símbolos, pois eles são implicitamente `static` / `Shared` .</span><span class="sxs-lookup"><span data-stu-id="5b6a5-171">If your group has `static` or `shared` in the `required_modifiers` property, the group will also include `const` symbols because they are implicitly `static`/`Shared`.</span></span> <span data-ttu-id="5b6a5-172">No entanto, se você não quiser que a `static` regra de nomenclatura se aplique a `const` símbolos, poderá criar uma nova regra de nomenclatura com um grupo de símbolos de `const` .</span><span class="sxs-lookup"><span data-stu-id="5b6a5-172">However, if you don't want the `static` naming rule to apply to `const` symbols, you can create a new naming rule with a symbol group of `const`.</span></span>

## <a name="naming-style-properties"></a><span data-ttu-id="5b6a5-173">Propriedades de estilo de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5b6a5-173">Naming style properties</span></span>

<span data-ttu-id="5b6a5-174">Um estilo de nomenclatura define as convenções que você deseja impor com a regra.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-174">A naming style defines the conventions you want to enforce with the rule.</span></span> <span data-ttu-id="5b6a5-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5b6a5-175">For example:</span></span>

* <span data-ttu-id="5b6a5-176">Colocar em maiúsculas com `PascalCase`</span><span class="sxs-lookup"><span data-stu-id="5b6a5-176">Capitalize with `PascalCase`</span></span>
* <span data-ttu-id="5b6a5-177">Começa com `m_`</span><span class="sxs-lookup"><span data-stu-id="5b6a5-177">Starts with `m_`</span></span>
* <span data-ttu-id="5b6a5-178">Termina com `_g`</span><span class="sxs-lookup"><span data-stu-id="5b6a5-178">Ends with `_g`</span></span>
* <span data-ttu-id="5b6a5-179">Separar palavras com `__`</span><span class="sxs-lookup"><span data-stu-id="5b6a5-179">Separate words with `__`</span></span>

<span data-ttu-id="5b6a5-180">Você pode definir as seguintes propriedades para um estilo de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="5b6a5-180">You can set the following properties for a naming style:</span></span>

| <span data-ttu-id="5b6a5-181">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5b6a5-181">Property</span></span> | <span data-ttu-id="5b6a5-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b6a5-182">Description</span></span> | <span data-ttu-id="5b6a5-183">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="5b6a5-183">Allowed values</span></span> | <span data-ttu-id="5b6a5-184">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5b6a5-184">Required</span></span> |
| -- | -- | -- | -- |
| `capitalization` | <span data-ttu-id="5b6a5-185">Estilo de capitalização de palavras dentro do símbolo</span><span class="sxs-lookup"><span data-stu-id="5b6a5-185">Capitalization style for words within the symbol</span></span> | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | <span data-ttu-id="5b6a5-186">Sim<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5b6a5-186">Yes<sup>1</sup></span></span> |
| `required_prefix` | <span data-ttu-id="5b6a5-187">Deve começar com estes caracteres</span><span class="sxs-lookup"><span data-stu-id="5b6a5-187">Must begin with these characters</span></span> | | <span data-ttu-id="5b6a5-188">Não</span><span class="sxs-lookup"><span data-stu-id="5b6a5-188">No</span></span> |
| `required_suffix` | <span data-ttu-id="5b6a5-189">Deve terminar com estes caracteres</span><span class="sxs-lookup"><span data-stu-id="5b6a5-189">Must end with these characters</span></span> | | <span data-ttu-id="5b6a5-190">Não</span><span class="sxs-lookup"><span data-stu-id="5b6a5-190">No</span></span> |
| `word_separator` | <span data-ttu-id="5b6a5-191">As palavras dentro do símbolo precisam ser separadas com este caractere</span><span class="sxs-lookup"><span data-stu-id="5b6a5-191">Words within the symbol need to be separated with this character</span></span> | | <span data-ttu-id="5b6a5-192">Não</span><span class="sxs-lookup"><span data-stu-id="5b6a5-192">No</span></span> |

<span data-ttu-id="5b6a5-193">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="5b6a5-193">**Notes:**</span></span>

1. <span data-ttu-id="5b6a5-194">É necessário especificar um estilo de uso de maiúsculas como parte do seu estilo de nomenclatura; caso contrário, o estilo de nomenclatura poderá ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-194">You must specify a capitalization style as part of your naming style, otherwise your naming style might be ignored.</span></span>

## <a name="default-naming-styles"></a><span data-ttu-id="5b6a5-195">Estilos de nomenclatura padrão</span><span class="sxs-lookup"><span data-stu-id="5b6a5-195">Default naming styles</span></span>

<span data-ttu-id="5b6a5-196">Se você não especificar nenhuma regra de nomenclatura personalizada, os seguintes estilos padrão serão usados:</span><span class="sxs-lookup"><span data-stu-id="5b6a5-196">If you don't specify any custom naming rules, the following default styles are used:</span></span>

- <span data-ttu-id="5b6a5-197">Para classes, estruturas, enumerações, propriedades e eventos com acessibilidade `public`, `private`, `internal`, `protected` ou `protected_internal`, o estilo de nomenclatura padrão é Pascal case.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-197">For classes, structs, enumerations, properties, and events with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case.</span></span>

- <span data-ttu-id="5b6a5-198">Para interfaces com acessibilidade `public`, `private`, `internal`, `protected` ou `protected_internal`, o estilo de nomenclatura padrão é Pascal case com o prefixo necessário **I**.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-198">For interfaces with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case with a required prefix of **I**.</span></span>

## <a name="example"></a><span data-ttu-id="5b6a5-199">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5b6a5-199">Example</span></span>

<span data-ttu-id="5b6a5-200">O arquivo *.editorconfig* a seguir contém uma convenção de nomenclatura que especifica que propriedades públicas, métodos, campos, eventos e delegados devem sempre ser escritos com maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-200">The following *.editorconfig* file contains a naming convention that specifies that public properties, methods, fields, events, and delegates must be capitalized.</span></span> <span data-ttu-id="5b6a5-201">Observe que esta convenção de nomenclatura especifica vários tipos de símbolo aos quais aplicar a regra, usando uma vírgula para separar os valores.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-201">Notice that this naming convention specifies multiple kinds of symbol to apply the rule to, using a comma to separate the values.</span></span>

```ini
[*.{cs,vb}]

# Defining the 'public_symbols' symbol group
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

# Defining the `first_word_upper_case_style` naming style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

# Defining the `public_members_must_be_capitalized` naming rule, by setting the symbol group to the 'public symbols' symbol group,
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
# setting the naming style to the `first_word_upper_case_style` naming style,
dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
# and setting the severity.
dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

## <a name="rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a><span data-ttu-id="5b6a5-202">ID da regra: "IDE1006" (violação da regra de nomenclatura)</span><span class="sxs-lookup"><span data-stu-id="5b6a5-202">Rule ID: "IDE1006" (Naming rule violation)</span></span>

<span data-ttu-id="5b6a5-203">Todas as opções de nomenclatura têm ID `IDE1006` de regra e título `Naming rule violation` .</span><span class="sxs-lookup"><span data-stu-id="5b6a5-203">All naming options have rule ID `IDE1006` and title `Naming rule violation`.</span></span> <span data-ttu-id="5b6a5-204">Você pode configurar a severidade de violações de nomenclatura globalmente em um arquivo EditorConfig com a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5b6a5-204">You can configure the severity of naming violations globally in an EditorConfig file with the following syntax:</span></span>

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

<span data-ttu-id="5b6a5-205">O valor de severidade deve ser `warning` ou `error` ser [imposto na compilação](../overview.md#code-style-analysis).</span><span class="sxs-lookup"><span data-stu-id="5b6a5-205">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="5b6a5-206">Para todos os valores de severidade possíveis, consulte [nível de severidade](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="5b6a5-206">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b6a5-207">Confira também</span><span class="sxs-lookup"><span data-stu-id="5b6a5-207">See also</span></span>

- [<span data-ttu-id="5b6a5-208">Regras de linguagem</span><span class="sxs-lookup"><span data-stu-id="5b6a5-208">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="5b6a5-209">Regras de formatação</span><span class="sxs-lookup"><span data-stu-id="5b6a5-209">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="5b6a5-210">Regras de nomenclatura Roslyn</span><span class="sxs-lookup"><span data-stu-id="5b6a5-210">Roslyn naming rules</span></span>](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [<span data-ttu-id="5b6a5-211">Referência de regras de estilo de código .NET</span><span class="sxs-lookup"><span data-stu-id="5b6a5-211">.NET code style rules reference</span></span>](index.md)
