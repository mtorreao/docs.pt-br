---
title: Regras de formatação de estilo de código
description: Saiba mais sobre as regras de estilo de código para formatação de recuos, espaços e novas linhas.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE0055
- formatting rules
helpviewer_keywords:
- IDE0055
- formatting code style rules [EditorConfig]
- formatting rules
- EditorConfig formatting conventions
ms.openlocfilehash: 61e6f6a6afdc6aaf9710eef3143af8ae700ef612
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "96585067"
---
# <a name="formatting-rules"></a><span data-ttu-id="737bd-103">Regras de formatação</span><span class="sxs-lookup"><span data-stu-id="737bd-103">Formatting rules</span></span>

<span data-ttu-id="737bd-104">As regras de formatação afetam como o recuo, os espaços e as novas linhas são alinhados em relação a construções de linguagem de programação .NET.</span><span class="sxs-lookup"><span data-stu-id="737bd-104">Formatting rules affect how indentation, spaces, and new lines are aligned around .NET programming language constructs.</span></span> <span data-ttu-id="737bd-105">As regras se enquadram nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="737bd-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="737bd-106">[Regras de formatação do .net](#net-formatting-rules): regras que se aplicam a C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="737bd-106">[.NET formatting rules](#net-formatting-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="737bd-107">Os nomes da opção EditorConfig para essas regras começam com o `dotnet_` prefixo.</span><span class="sxs-lookup"><span data-stu-id="737bd-107">The EditorConfig option names for these rules start with `dotnet_` prefix.</span></span>
- <span data-ttu-id="737bd-108">[Regras de formatação em c#](#c-formatting-rules): regras que são específicas apenas para a linguagem C#.</span><span class="sxs-lookup"><span data-stu-id="737bd-108">[C# formatting rules](#c-formatting-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="737bd-109">Os nomes da opção EditorConfig para essas regras começam com o `csharp_` prefixo.</span><span class="sxs-lookup"><span data-stu-id="737bd-109">The EditorConfig option names for these rules start with `csharp_` prefix.</span></span>

## <a name="rule-id-ide0055-fix-formatting"></a><span data-ttu-id="737bd-110">ID da regra: "IDE0055" (corrigir formatação)</span><span class="sxs-lookup"><span data-stu-id="737bd-110">Rule ID: "IDE0055" (Fix formatting)</span></span>

<span data-ttu-id="737bd-111">Todas as opções de formatação têm a ID e o título da regra `IDE0055` `Fix formatting` .</span><span class="sxs-lookup"><span data-stu-id="737bd-111">All formatting options have rule ID `IDE0055` and title `Fix formatting`.</span></span> <span data-ttu-id="737bd-112">Defina a severidade de uma violação de formatação em um arquivo EditorConfig usando a seguinte linha de configuração.</span><span class="sxs-lookup"><span data-stu-id="737bd-112">Set the severity of a formatting violation in an EditorConfig file using the following configuration line.</span></span>

```ini
dotnet_diagnostic.IDE0055.severity = <severity value>
```

<span data-ttu-id="737bd-113">O valor de severidade deve ser `warning` ou `error` ser [imposto na compilação](../overview.md#code-style-analysis).</span><span class="sxs-lookup"><span data-stu-id="737bd-113">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="737bd-114">Para todos os valores de severidade possíveis, consulte [nível de severidade](../configuration-options.md#severity-level).</span><span class="sxs-lookup"><span data-stu-id="737bd-114">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="option-format"></a><span data-ttu-id="737bd-115">Formato da opção</span><span class="sxs-lookup"><span data-stu-id="737bd-115">Option format</span></span>

<span data-ttu-id="737bd-116">As opções para regras de formatação podem ser especificadas em um arquivo EditorConfig com o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="737bd-116">Options for formatting rules can be specified in an EditorConfig file with the following format:</span></span>

`rule_name = value`

<span data-ttu-id="737bd-117">Para muitas regras, você especifica `true` (preferir esse estilo) ou `false` (não preferir esse estilo) para `value`.</span><span class="sxs-lookup"><span data-stu-id="737bd-117">For many rules, you specify either `true` (prefer this style) or `false` (do not prefer this style) for `value`.</span></span> <span data-ttu-id="737bd-118">Para outras regras, você especifica um valor como `flush_left` ou `before_and_after` para descrever quando e onde aplicar a regra.</span><span class="sxs-lookup"><span data-stu-id="737bd-118">For other rules, you specify a value such as `flush_left` or `before_and_after` to describe when and where to apply the rule.</span></span> <span data-ttu-id="737bd-119">Você não especifica uma gravidade.</span><span class="sxs-lookup"><span data-stu-id="737bd-119">You don't specify a severity.</span></span>

## <a name="net-formatting-rules"></a><span data-ttu-id="737bd-120">Regras de formatação do .NET</span><span class="sxs-lookup"><span data-stu-id="737bd-120">.NET formatting rules</span></span>

<span data-ttu-id="737bd-121">As regras de formatação nesta seção se aplicam ao C# e ao Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="737bd-121">The formatting rules in this section apply to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="737bd-122">Organizar usando</span><span class="sxs-lookup"><span data-stu-id="737bd-122">Organize usings</span></span>](#organize-using-directives)
  - <span data-ttu-id="737bd-123">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="737bd-123">dotnet_sort_system_directives_first</span></span>
  - <span data-ttu-id="737bd-124">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="737bd-124">dotnet_separate_import_directive_groups</span></span>

### <a name="organize-using-directives"></a><span data-ttu-id="737bd-125">Organizar usando diretivas</span><span class="sxs-lookup"><span data-stu-id="737bd-125">Organize using directives</span></span>

<span data-ttu-id="737bd-126">Essas regras de formatação referem-se à classificação e à exibição de diretivas `using` e instruções `Imports`.</span><span class="sxs-lookup"><span data-stu-id="737bd-126">These formatting rules concern the sorting and display of `using` directives and `Imports` statements.</span></span>

<span data-ttu-id="737bd-127">Exemplo de arquivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="737bd-127">Example *.editorconfig* file:</span></span>

```ini
# .NET formatting rules
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = true
```

#### <a name="dotnet_sort_system_directives_first"></a><span data-ttu-id="737bd-128">dotnet\_sort\_system\_directives_first</span><span class="sxs-lookup"><span data-stu-id="737bd-128">dotnet\_sort\_system\_directives_first</span></span>

|<span data-ttu-id="737bd-129">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-129">Property</span></span>|<span data-ttu-id="737bd-130">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-130">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-131">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-131">**Option name**</span></span> | <span data-ttu-id="737bd-132">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="737bd-132">dotnet_sort_system_directives_first</span></span> |
| <span data-ttu-id="737bd-133">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-133">**Applicable languages**</span></span> | <span data-ttu-id="737bd-134">C# e Visual Basic</span><span class="sxs-lookup"><span data-stu-id="737bd-134">C# and Visual Basic</span></span> |
| <span data-ttu-id="737bd-135">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-135">**Introduced version**</span></span> | <span data-ttu-id="737bd-136">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-136">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-137">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-137">**Option values**</span></span> | <span data-ttu-id="737bd-138">`true` -Classifique `System.*` `using` as diretivas em ordem alfabética e coloque-as antes de outras usando diretivas.</span><span class="sxs-lookup"><span data-stu-id="737bd-138">`true` - Sort `System.*` `using` directives alphabetically, and place them before other using directives.</span></span><br /><br /><span data-ttu-id="737bd-139">`false` -Não coloque `System.*` `using` diretivas antes de outras `using` diretivas.</span><span class="sxs-lookup"><span data-stu-id="737bd-139">`false` - Do not place `System.*` `using` directives before other `using` directives.</span></span> |

<span data-ttu-id="737bd-140">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-140">Code examples:</span></span>

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

#### <a name="dotnet_separate_import_directive_groups"></a><span data-ttu-id="737bd-141">dotnet\_separate\_import\_directive\_groups</span><span class="sxs-lookup"><span data-stu-id="737bd-141">dotnet\_separate\_import\_directive\_groups</span></span>

|<span data-ttu-id="737bd-142">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-142">Property</span></span>|<span data-ttu-id="737bd-143">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-143">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-144">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-144">**Option name**</span></span> | <span data-ttu-id="737bd-145">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="737bd-145">dotnet_separate_import_directive_groups</span></span> |
| <span data-ttu-id="737bd-146">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-146">**Applicable languages**</span></span> | <span data-ttu-id="737bd-147">C# e Visual Basic</span><span class="sxs-lookup"><span data-stu-id="737bd-147">C# and Visual Basic</span></span> |
| <span data-ttu-id="737bd-148">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-148">**Introduced version**</span></span> | <span data-ttu-id="737bd-149">Visual Studio 2017 versão 15.5</span><span class="sxs-lookup"><span data-stu-id="737bd-149">Visual Studio 2017 version 15.5</span></span> |
| <span data-ttu-id="737bd-150">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-150">**Option values**</span></span> | <span data-ttu-id="737bd-151">`true` – coloque uma linha em branco entre os grupos de diretivas `using`.</span><span class="sxs-lookup"><span data-stu-id="737bd-151">`true` - Place a blank line between `using` directive groups.</span></span><br /><br /><span data-ttu-id="737bd-152">`false` – não coloque uma linha em branco entre os grupos de diretivas `using`.</span><span class="sxs-lookup"><span data-stu-id="737bd-152">`false` - Do not place a blank line between `using` directive groups.</span></span> |

<span data-ttu-id="737bd-153">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-153">Code examples:</span></span>

```csharp
// dotnet_separate_import_directive_groups = true
using System.Collections.Generic;
using System.Threading.Tasks;

using Octokit;

// dotnet_separate_import_directive_groups = false
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;
```

## <a name="c-formatting-rules"></a><span data-ttu-id="737bd-154">Regras de formatação em C#</span><span class="sxs-lookup"><span data-stu-id="737bd-154">C# formatting rules</span></span>

<span data-ttu-id="737bd-155">As regras de formatação nesta seção aplicam-se somente a código em C#.</span><span class="sxs-lookup"><span data-stu-id="737bd-155">The formatting rules in this section apply only to C# code.</span></span>

- [<span data-ttu-id="737bd-156">Opções de nova linha</span><span class="sxs-lookup"><span data-stu-id="737bd-156">Newline options</span></span>](#new-line-options)
  - <span data-ttu-id="737bd-157">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="737bd-157">csharp_new_line_before_open_brace</span></span>
  - <span data-ttu-id="737bd-158">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="737bd-158">csharp_new_line_before_else</span></span>
  - <span data-ttu-id="737bd-159">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="737bd-159">csharp_new_line_before_catch</span></span>
  - <span data-ttu-id="737bd-160">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="737bd-160">csharp_new_line_before_finally</span></span>
  - <span data-ttu-id="737bd-161">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="737bd-161">csharp_new_line_before_members_in_object_initializers</span></span>
  - <span data-ttu-id="737bd-162">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="737bd-162">csharp_new_line_before_members_in_anonymous_types</span></span>
  - <span data-ttu-id="737bd-163">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="737bd-163">csharp_new_line_between_query_expression_clauses</span></span>
- [<span data-ttu-id="737bd-164">Opções de recuo</span><span class="sxs-lookup"><span data-stu-id="737bd-164">Indentation options</span></span>](#indentation-options)
  - <span data-ttu-id="737bd-165">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="737bd-165">csharp_indent_case_contents</span></span>
  - <span data-ttu-id="737bd-166">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="737bd-166">csharp_indent_switch_labels</span></span>
  - <span data-ttu-id="737bd-167">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="737bd-167">csharp_indent_labels</span></span>
  - <span data-ttu-id="737bd-168">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="737bd-168">csharp_indent_block_contents</span></span>
  - <span data-ttu-id="737bd-169">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="737bd-169">csharp_indent_braces</span></span>
  - <span data-ttu-id="737bd-170">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="737bd-170">csharp_indent_case_contents_when_block</span></span>
- [<span data-ttu-id="737bd-171">Opções de espaçamento</span><span class="sxs-lookup"><span data-stu-id="737bd-171">Spacing options</span></span>](#spacing-options)
  - <span data-ttu-id="737bd-172">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="737bd-172">csharp_space_after_cast</span></span>
  - <span data-ttu-id="737bd-173">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-173">csharp_space_after_keywords_in_control_flow_statements</span></span>
  - <span data-ttu-id="737bd-174">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-174">csharp_space_between_parentheses</span></span>
  - <span data-ttu-id="737bd-175">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="737bd-175">csharp_space_before_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="737bd-176">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="737bd-176">csharp_space_after_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="737bd-177">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="737bd-177">csharp_space_around_binary_operators</span></span>
  - <span data-ttu-id="737bd-178">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-178">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>
  - <span data-ttu-id="737bd-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="737bd-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="737bd-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>
  - <span data-ttu-id="737bd-181">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-181">csharp_space_between_method_call_parameter_list_parentheses</span></span>
  - <span data-ttu-id="737bd-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="737bd-183">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="737bd-183">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>
  - <span data-ttu-id="737bd-184">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="737bd-184">csharp_space_after_comma</span></span>
  - <span data-ttu-id="737bd-185">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="737bd-185">csharp_space_before_comma</span></span>
  - <span data-ttu-id="737bd-186">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="737bd-186">csharp_space_after_dot</span></span>
  - <span data-ttu-id="737bd-187">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="737bd-187">csharp_space_before_dot</span></span>
  - <span data-ttu-id="737bd-188">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="737bd-188">csharp_space_after_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="737bd-189">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="737bd-189">csharp_space_before_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="737bd-190">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-190">csharp_space_around_declaration_statements</span></span>
  - <span data-ttu-id="737bd-191">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-191">csharp_space_before_open_square_brackets</span></span>
  - <span data-ttu-id="737bd-192">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-192">csharp_space_between_empty_square_brackets</span></span>
  - <span data-ttu-id="737bd-193">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-193">csharp_space_between_square_brackets</span></span>
- [<span data-ttu-id="737bd-194">Encapsular opções</span><span class="sxs-lookup"><span data-stu-id="737bd-194">Wrap options</span></span>](#wrap-options)
  - <span data-ttu-id="737bd-195">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-195">csharp_preserve_single_line_statements</span></span>
  - <span data-ttu-id="737bd-196">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="737bd-196">csharp_preserve_single_line_blocks</span></span>
- [<span data-ttu-id="737bd-197">Usando opções de diretiva</span><span class="sxs-lookup"><span data-stu-id="737bd-197">Using directive options</span></span>](#using-directive-options)
  - <span data-ttu-id="737bd-198">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="737bd-198">csharp_using_directive_placement</span></span>

### <a name="new-line-options"></a><span data-ttu-id="737bd-199">Opções de nova linha</span><span class="sxs-lookup"><span data-stu-id="737bd-199">New-line options</span></span>

<span data-ttu-id="737bd-200">Essas regras de formatação envolvem o uso de novas linhas para formatar o código.</span><span class="sxs-lookup"><span data-stu-id="737bd-200">These formatting rules concern the use of new lines to format code.</span></span>

<span data-ttu-id="737bd-201">Exemplo de arquivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="737bd-201">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### <a name="csharp_new_line_before_open_brace"></a><span data-ttu-id="737bd-202">csharp\_new\_line\_before\_open_brace</span><span class="sxs-lookup"><span data-stu-id="737bd-202">csharp\_new\_line\_before\_open_brace</span></span>

<span data-ttu-id="737bd-203">Essa regra está relacionada a se uma chave de abertura `{` devem ser colocada na mesma linha que a do código anterior ou em uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="737bd-203">This rule concerns whether an open brace `{` should be placed on the same line as the preceding code, or on a new line.</span></span> <span data-ttu-id="737bd-204">Para essa regra, você especifica **all**, **none** ou um ou mais elementos de código, como **métodos** ou **propriedades**, para definir quando essa regra deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="737bd-204">For this rule, you specify **all**, **none**, or one or more code elements such as **methods** or **properties**, to define when this rule should be applied.</span></span> <span data-ttu-id="737bd-205">Para especificar vários elementos de código, separe-os com uma vírgula (,).</span><span class="sxs-lookup"><span data-stu-id="737bd-205">To specify multiple code elements, separate them with a comma (,).</span></span>

|<span data-ttu-id="737bd-206">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-206">Property</span></span>|<span data-ttu-id="737bd-207">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-207">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-208">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-208">**Option name**</span></span> | <span data-ttu-id="737bd-209">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="737bd-209">csharp_new_line_before_open_brace</span></span> |
| <span data-ttu-id="737bd-210">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-210">**Applicable languages**</span></span> | <span data-ttu-id="737bd-211">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-211">C#</span></span> |
| <span data-ttu-id="737bd-212">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-212">**Introduced version**</span></span> | <span data-ttu-id="737bd-213">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-213">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-214">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-214">**Option values**</span></span> | <span data-ttu-id="737bd-215">`all` – requer que as chaves estejam em uma nova linha para todas as expressões (estilo "Allman").</span><span class="sxs-lookup"><span data-stu-id="737bd-215">`all` - Require braces to be on a new line for all expressions ("Allman" style).</span></span><br /><br /><span data-ttu-id="737bd-216">`none` – requer que as chaves estejam na mesma linha para todas as expressões ("K&R").</span><span class="sxs-lookup"><span data-stu-id="737bd-216">`none` - Require braces to be on the same line for all expressions ("K&R").</span></span><br /><br /><span data-ttu-id="737bd-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` – requer que as chaves estejam em uma nova linha para o elemento de código especificado (estilo "Allman").</span><span class="sxs-lookup"><span data-stu-id="737bd-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - Require braces to be on a new line for the specified code element ("Allman" style).</span></span> |

<span data-ttu-id="737bd-218">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-218">Code examples:</span></span>

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

#### <a name="csharp_new_line_before_else"></a><span data-ttu-id="737bd-219">csharp\_new\_line\_before_else</span><span class="sxs-lookup"><span data-stu-id="737bd-219">csharp\_new\_line\_before_else</span></span>

|<span data-ttu-id="737bd-220">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-220">Property</span></span>|<span data-ttu-id="737bd-221">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-221">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-222">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-222">**Option name**</span></span> | <span data-ttu-id="737bd-223">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="737bd-223">csharp_new_line_before_else</span></span> |
| <span data-ttu-id="737bd-224">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-224">**Applicable languages**</span></span> | <span data-ttu-id="737bd-225">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-225">C#</span></span> |
| <span data-ttu-id="737bd-226">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-226">**Introduced version**</span></span> | <span data-ttu-id="737bd-227">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-227">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-228">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-228">**Option values**</span></span> | <span data-ttu-id="737bd-229">`true` – insira as instruções `else` em uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="737bd-229">`true` - Place `else` statements on a new line.</span></span><br /><br /><span data-ttu-id="737bd-230">`false` – insira as instruções `else` na mesma linha.</span><span class="sxs-lookup"><span data-stu-id="737bd-230">`false` - Place `else` statements on the same line.</span></span> |

<span data-ttu-id="737bd-231">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-231">Code examples:</span></span>

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

#### <a name="csharp_new_line_before_catch"></a><span data-ttu-id="737bd-232">csharp\_new\_line\_before_catch</span><span class="sxs-lookup"><span data-stu-id="737bd-232">csharp\_new\_line\_before_catch</span></span>

|<span data-ttu-id="737bd-233">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-233">Property</span></span>|<span data-ttu-id="737bd-234">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-234">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-235">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-235">**Option name**</span></span> | <span data-ttu-id="737bd-236">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="737bd-236">csharp_new_line_before_catch</span></span> |
| <span data-ttu-id="737bd-237">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-237">**Applicable languages**</span></span> | <span data-ttu-id="737bd-238">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-238">C#</span></span> |
| <span data-ttu-id="737bd-239">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-239">**Introduced version**</span></span> | <span data-ttu-id="737bd-240">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-240">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-241">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-241">**Option values**</span></span> | <span data-ttu-id="737bd-242">`true` – insira as instruções `catch` em uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="737bd-242">`true` - Place `catch` statements on a new line.</span></span><br /><br /><span data-ttu-id="737bd-243">`false` – insira as instruções `catch` na mesma linha.</span><span class="sxs-lookup"><span data-stu-id="737bd-243">`false` - Place `catch` statements on the same line.</span></span> |

<span data-ttu-id="737bd-244">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-244">Code examples:</span></span>

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

#### <a name="csharp_new_line_before_finally"></a><span data-ttu-id="737bd-245">csharp\_new\_line\_before_finally</span><span class="sxs-lookup"><span data-stu-id="737bd-245">csharp\_new\_line\_before_finally</span></span>

|<span data-ttu-id="737bd-246">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-246">Property</span></span>|<span data-ttu-id="737bd-247">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-247">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-248">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-248">**Option name**</span></span> | <span data-ttu-id="737bd-249">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="737bd-249">csharp_new_line_before_finally</span></span> |
| <span data-ttu-id="737bd-250">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-250">**Applicable languages**</span></span> | <span data-ttu-id="737bd-251">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-251">C#</span></span> |
| <span data-ttu-id="737bd-252">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-252">**Introduced version**</span></span> | <span data-ttu-id="737bd-253">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-253">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-254">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-254">**Option values**</span></span> | <span data-ttu-id="737bd-255">`true` – exigir que as instruções `finally` estejam em uma nova linha após a chave de fechamento.</span><span class="sxs-lookup"><span data-stu-id="737bd-255">`true` - Require `finally` statements to be on a new line after the closing brace.</span></span><br /><br /><span data-ttu-id="737bd-256">`false` – exigir que as instruções `finally` estejam na mesma linha como a chave de fechamento.</span><span class="sxs-lookup"><span data-stu-id="737bd-256">`false` - Require `finally` statements to be on the same line as the closing brace.</span></span> |

<span data-ttu-id="737bd-257">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-257">Code examples:</span></span>

```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

#### <a name="csharp_new_line_before_members_in_object_initializers"></a><span data-ttu-id="737bd-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span><span class="sxs-lookup"><span data-stu-id="737bd-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span></span>

|<span data-ttu-id="737bd-259">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-259">Property</span></span>|<span data-ttu-id="737bd-260">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-260">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-261">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-261">**Option name**</span></span> | <span data-ttu-id="737bd-262">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="737bd-262">csharp_new_line_before_members_in_object_initializers</span></span> |
| <span data-ttu-id="737bd-263">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-263">**Applicable languages**</span></span> | <span data-ttu-id="737bd-264">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-264">C#</span></span> |
| <span data-ttu-id="737bd-265">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-265">**Introduced version**</span></span> | <span data-ttu-id="737bd-266">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-266">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-267">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-267">**Option values**</span></span> | <span data-ttu-id="737bd-268">`true` – exigir que membros dos inicializadores de objetos estejam em linhas separadas</span><span class="sxs-lookup"><span data-stu-id="737bd-268">`true` - Require members of object initializers to be on separate lines</span></span><br /><br /><span data-ttu-id="737bd-269">`false` – exigir que membros dos inicializadores de objetos estejam na mesma linha</span><span class="sxs-lookup"><span data-stu-id="737bd-269">`false` - Require members of object initializers to be on the same line</span></span> |

<span data-ttu-id="737bd-270">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-270">Code examples:</span></span>

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

#### <a name="csharp_new_line_before_members_in_anonymous_types"></a><span data-ttu-id="737bd-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="737bd-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span></span>

|<span data-ttu-id="737bd-272">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-272">Property</span></span>|<span data-ttu-id="737bd-273">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-273">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-274">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-274">**Option name**</span></span> | <span data-ttu-id="737bd-275">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="737bd-275">csharp_new_line_before_members_in_anonymous_types</span></span> |
| <span data-ttu-id="737bd-276">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-276">**Applicable languages**</span></span> | <span data-ttu-id="737bd-277">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-277">C#</span></span> |
| <span data-ttu-id="737bd-278">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-278">**Introduced version**</span></span> | <span data-ttu-id="737bd-279">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-279">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-280">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-280">**Option values**</span></span> | <span data-ttu-id="737bd-281">`true` – exigir que membros de tipos anônimos estejam em linhas separadas</span><span class="sxs-lookup"><span data-stu-id="737bd-281">`true` - Require members of anonymous types to be on separate lines</span></span><br /><br /><span data-ttu-id="737bd-282">`false` – exigir que membros de tipos anônimos estejam na mesma linha</span><span class="sxs-lookup"><span data-stu-id="737bd-282">`false` - Require members of anonymous types to be on the same line</span></span> |

<span data-ttu-id="737bd-283">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-283">Code examples:</span></span>

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

#### <a name="csharp_new_line_between_query_expression_clauses"></a><span data-ttu-id="737bd-284">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="737bd-284">csharp_new_line_between_query_expression_clauses</span></span>

|<span data-ttu-id="737bd-285">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-285">Property</span></span>|<span data-ttu-id="737bd-286">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-286">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-287">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-287">**Option name**</span></span> | <span data-ttu-id="737bd-288">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="737bd-288">csharp_new_line_between_query_expression_clauses</span></span> |
| <span data-ttu-id="737bd-289">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-289">**Applicable languages**</span></span> | <span data-ttu-id="737bd-290">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-290">C#</span></span> |
| <span data-ttu-id="737bd-291">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-291">**Introduced version**</span></span> | <span data-ttu-id="737bd-292">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-292">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-293">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-293">**Option values**</span></span> | <span data-ttu-id="737bd-294">`true` – exigir que elementos das cláusulas de expressão de consulta estejam em linhas separadas</span><span class="sxs-lookup"><span data-stu-id="737bd-294">`true` - Require elements of query expression clauses to be on separate lines</span></span><br /><br /><span data-ttu-id="737bd-295">`false` – exigir que elementos das cláusulas de expressão de consulta estejam na mesma linha</span><span class="sxs-lookup"><span data-stu-id="737bd-295">`false` - Require elements of query expression clauses to be on the same line</span></span> |

<span data-ttu-id="737bd-296">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-296">Code examples:</span></span>

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

### <a name="indentation-options"></a><span data-ttu-id="737bd-297">Opções de recuo</span><span class="sxs-lookup"><span data-stu-id="737bd-297">Indentation options</span></span>

<span data-ttu-id="737bd-298">Essas regras de formatação envolvem o uso de recuo para formatar o código.</span><span class="sxs-lookup"><span data-stu-id="737bd-298">These formatting rules concern the use of indentation to format code.</span></span>

<span data-ttu-id="737bd-299">Exemplo de arquivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="737bd-299">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
csharp_indent_block_contents = true
csharp_indent_braces = false
csharp_indent_case_contents_when_block = true
```

#### <a name="csharp_indent_case_contents"></a><span data-ttu-id="737bd-300">csharp\_indent\_case_contents</span><span class="sxs-lookup"><span data-stu-id="737bd-300">csharp\_indent\_case_contents</span></span>

|<span data-ttu-id="737bd-301">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-301">Property</span></span>|<span data-ttu-id="737bd-302">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-302">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-303">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-303">**Option name**</span></span> | <span data-ttu-id="737bd-304">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="737bd-304">csharp_indent_case_contents</span></span> |
| <span data-ttu-id="737bd-305">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-305">**Applicable languages**</span></span> | <span data-ttu-id="737bd-306">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-306">C#</span></span> |
| <span data-ttu-id="737bd-307">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-307">**Introduced version**</span></span> | <span data-ttu-id="737bd-308">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-308">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-309">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-309">**Option values**</span></span> | <span data-ttu-id="737bd-310">`true` – recuar `switch` conteúdo de caso</span><span class="sxs-lookup"><span data-stu-id="737bd-310">`true` - Indent `switch` case contents</span></span><br /><br /><span data-ttu-id="737bd-311">`false` – não recuar `switch` conteúdo de caso</span><span class="sxs-lookup"><span data-stu-id="737bd-311">`false` - Do not indent `switch` case contents</span></span> |

- <span data-ttu-id="737bd-312">Quando essa regra é definida como **true**, i.</span><span class="sxs-lookup"><span data-stu-id="737bd-312">When this rule is set to **true**, i.</span></span>
- <span data-ttu-id="737bd-313">Quando essa regra é definida como **true**, d.</span><span class="sxs-lookup"><span data-stu-id="737bd-313">When this rule is set to **false**, d.</span></span>

<span data-ttu-id="737bd-314">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-314">Code examples:</span></span>

```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="csharp_indent_switch_labels"></a><span data-ttu-id="737bd-315">csharp\_indent\_switch_labels</span><span class="sxs-lookup"><span data-stu-id="737bd-315">csharp\_indent\_switch_labels</span></span>

|<span data-ttu-id="737bd-316">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-316">Property</span></span>|<span data-ttu-id="737bd-317">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-317">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-318">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-318">**Option name**</span></span> | <span data-ttu-id="737bd-319">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="737bd-319">csharp_indent_switch_labels</span></span> |
| <span data-ttu-id="737bd-320">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-320">**Applicable languages**</span></span> | <span data-ttu-id="737bd-321">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-321">C#</span></span> |
| <span data-ttu-id="737bd-322">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-322">**Introduced version**</span></span> | <span data-ttu-id="737bd-323">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-323">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-324">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-324">**Option values**</span></span> | <span data-ttu-id="737bd-325">`true` – recuar `switch` rótulos</span><span class="sxs-lookup"><span data-stu-id="737bd-325">`true` - Indent `switch` labels</span></span><br /><br /><span data-ttu-id="737bd-326">`false` – não recuar `switch` rótulos</span><span class="sxs-lookup"><span data-stu-id="737bd-326">`false` - Do not indent `switch` labels</span></span> |

<span data-ttu-id="737bd-327">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-327">Code examples:</span></span>

```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="csharp_indent_labels"></a><span data-ttu-id="737bd-328">csharp\_indent_labels</span><span class="sxs-lookup"><span data-stu-id="737bd-328">csharp\_indent_labels</span></span>

|<span data-ttu-id="737bd-329">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-329">Property</span></span>|<span data-ttu-id="737bd-330">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-330">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-331">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-331">**Option name**</span></span> | <span data-ttu-id="737bd-332">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="737bd-332">csharp_indent_labels</span></span> |
| <span data-ttu-id="737bd-333">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-333">**Applicable languages**</span></span> | <span data-ttu-id="737bd-334">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-334">C#</span></span> |
| <span data-ttu-id="737bd-335">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-335">**Introduced version**</span></span> | <span data-ttu-id="737bd-336">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-336">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-337">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-337">**Option values**</span></span> | <span data-ttu-id="737bd-338">`flush_left` – os rótulos são posicionados na coluna mais à esquerda</span><span class="sxs-lookup"><span data-stu-id="737bd-338">`flush_left` - Labels are placed at the leftmost column</span></span><br /><br /><span data-ttu-id="737bd-339">`one_less_than_current` – os rótulos são posicionados em um recuo a menos do que o contexto atual</span><span class="sxs-lookup"><span data-stu-id="737bd-339">`one_less_than_current` - Labels are placed at one less indent to the current context</span></span><br /><br /><span data-ttu-id="737bd-340">`no_change` – os rótulos são posicionados no mesmo recuo do contexto atual</span><span class="sxs-lookup"><span data-stu-id="737bd-340">`no_change` - Labels are placed at the same indent as the current context</span></span> |

<span data-ttu-id="737bd-341">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-341">Code examples:</span></span>

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

#### <a name="csharp_indent_block_contents"></a><span data-ttu-id="737bd-342">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="737bd-342">csharp_indent_block_contents</span></span>

|<span data-ttu-id="737bd-343">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-343">Property</span></span>|<span data-ttu-id="737bd-344">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-344">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-345">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-345">**Option name**</span></span> | <span data-ttu-id="737bd-346">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="737bd-346">csharp_indent_block_contents</span></span> |
| <span data-ttu-id="737bd-347">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-347">**Applicable languages**</span></span> | <span data-ttu-id="737bd-348">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-348">C#</span></span> |
| <span data-ttu-id="737bd-349">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-349">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="737bd-350">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-350">Code examples:</span></span>

```csharp
// csharp_indent_block_contents = true
static void Hello()
{
    Console.WriteLine("Hello");
}

// csharp_indent_block_contents = false
static void Hello()
{
Console.WriteLine("Hello");
}
```

#### <a name="csharp_indent_braces"></a><span data-ttu-id="737bd-351">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="737bd-351">csharp_indent_braces</span></span>

|<span data-ttu-id="737bd-352">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-352">Property</span></span>|<span data-ttu-id="737bd-353">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-353">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-354">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-354">**Option name**</span></span> | <span data-ttu-id="737bd-355">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="737bd-355">csharp_indent_braces</span></span> |
| <span data-ttu-id="737bd-356">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-356">**Applicable languages**</span></span> | <span data-ttu-id="737bd-357">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-357">C#</span></span> |
| <span data-ttu-id="737bd-358">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-358">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="737bd-359">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-359">Code examples:</span></span>

```csharp
// csharp_indent_braces = true
static void Hello()
    {
    Console.WriteLine("Hello");
    }

// csharp_indent_braces = false
static void Hello()
{
    Console.WriteLine("Hello");
}
```

#### <a name="csharp_indent_case_contents_when_block"></a><span data-ttu-id="737bd-360">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="737bd-360">csharp_indent_case_contents_when_block</span></span>

|<span data-ttu-id="737bd-361">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-361">Property</span></span>|<span data-ttu-id="737bd-362">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-362">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-363">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-363">**Option name**</span></span> | <span data-ttu-id="737bd-364">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="737bd-364">csharp_indent_case_contents_when_block</span></span> |
| <span data-ttu-id="737bd-365">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-365">**Applicable languages**</span></span> | <span data-ttu-id="737bd-366">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-366">C#</span></span> |
| <span data-ttu-id="737bd-367">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-367">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="737bd-368">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-368">Code examples:</span></span>

```csharp
// csharp_indent_case_contents_when_block = true
case 0:
    {
        Console.WriteLine("Hello");
        break;
    }

// csharp_indent_case_contents_when_block = false
case 0:
{
    Console.WriteLine("Hello");
    break;
}
```

### <a name="spacing-options"></a><span data-ttu-id="737bd-369">Opções de espaçamento</span><span class="sxs-lookup"><span data-stu-id="737bd-369">Spacing options</span></span>

<span data-ttu-id="737bd-370">Essas regras de formatação envolvem o uso de caracteres de espaço para formatar o código.</span><span class="sxs-lookup"><span data-stu-id="737bd-370">These formatting rules concern the use of space characters to format code.</span></span>

<span data-ttu-id="737bd-371">Exemplo de arquivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="737bd-371">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_parentheses = control_flow_statements, type_casts
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_around_binary_operators = before_and_after
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_declaration_name_and_open_parenthesis = false
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_method_call_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_after_comma = true
csharp_space_before_comma = false
csharp_space_after_dot = false
csharp_space_before_dot = false
csharp_space_after_semicolon_in_for_statement = true
csharp_space_before_semicolon_in_for_statement = false
csharp_space_around_declaration_statements = false
csharp_space_before_open_square_brackets = false
csharp_space_between_empty_square_brackets = false
csharp_space_between_square_brackets = false
```

#### <a name="csharp_space_after_cast"></a><span data-ttu-id="737bd-372">csharp\_space\_after_cast</span><span class="sxs-lookup"><span data-stu-id="737bd-372">csharp\_space\_after_cast</span></span>

|<span data-ttu-id="737bd-373">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-373">Property</span></span>|<span data-ttu-id="737bd-374">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-374">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-375">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-375">**Option name**</span></span> | <span data-ttu-id="737bd-376">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="737bd-376">csharp_space_after_cast</span></span> |
| <span data-ttu-id="737bd-377">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-377">**Applicable languages**</span></span> | <span data-ttu-id="737bd-378">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-378">C#</span></span> |
| <span data-ttu-id="737bd-379">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-379">**Introduced version**</span></span> | <span data-ttu-id="737bd-380">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-380">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-381">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-381">**Option values**</span></span> | <span data-ttu-id="737bd-382">`true` – inserir um caractere de espaço entre uma conversão e o valor</span><span class="sxs-lookup"><span data-stu-id="737bd-382">`true` - Place a space character between a cast and the value</span></span><br /><br /><span data-ttu-id="737bd-383">`false` – Remover o espaço entre a conversão e o valor</span><span class="sxs-lookup"><span data-stu-id="737bd-383">`false` - Remove space between the cast and the value</span></span> |

<span data-ttu-id="737bd-384">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-384">Code examples:</span></span>

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

#### <a name="csharp_space_after_keywords_in_control_flow_statements"></a><span data-ttu-id="737bd-385">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-385">csharp_space_after_keywords_in_control_flow_statements</span></span>

|<span data-ttu-id="737bd-386">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-386">Property</span></span>|<span data-ttu-id="737bd-387">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-387">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-388">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-388">**Option name**</span></span> | <span data-ttu-id="737bd-389">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-389">csharp_space_after_keywords_in_control_flow_statements</span></span> |
| <span data-ttu-id="737bd-390">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-390">**Applicable languages**</span></span> | <span data-ttu-id="737bd-391">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-391">C#</span></span> |
| <span data-ttu-id="737bd-392">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-392">**Introduced version**</span></span> | <span data-ttu-id="737bd-393">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-393">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-394">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-394">**Option values**</span></span> | <span data-ttu-id="737bd-395">`true` – inserir um caractere de espaço após uma palavra-chave em uma instrução de fluxo de controle, como um loop `for`</span><span class="sxs-lookup"><span data-stu-id="737bd-395">`true` - Place a space character after a keyword in a control flow statement such as a `for` loop</span></span><br /><br /><span data-ttu-id="737bd-396">`false` – remover um espaço após uma palavra-chave em uma instrução de fluxo de controle, como um loop `for`</span><span class="sxs-lookup"><span data-stu-id="737bd-396">`false` - Remove space after a keyword in a control flow statement such as a `for` loop</span></span> |

<span data-ttu-id="737bd-397">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-397">Code examples:</span></span>

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

#### <a name="csharp_space_between_parentheses"></a><span data-ttu-id="737bd-398">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-398">csharp_space_between_parentheses</span></span>

|<span data-ttu-id="737bd-399">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-399">Property</span></span>|<span data-ttu-id="737bd-400">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-400">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-401">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-401">**Option name**</span></span> | <span data-ttu-id="737bd-402">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-402">csharp_space_between_parentheses</span></span> |
| <span data-ttu-id="737bd-403">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-403">**Applicable languages**</span></span> | <span data-ttu-id="737bd-404">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-404">C#</span></span> |
| <span data-ttu-id="737bd-405">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-405">**Introduced version**</span></span> | <span data-ttu-id="737bd-406">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-406">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-407">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-407">**Option values**</span></span> | <span data-ttu-id="737bd-408">`control_flow_statements` – inserir espaço entre parênteses das instruções de fluxo de controle</span><span class="sxs-lookup"><span data-stu-id="737bd-408">`control_flow_statements` - Place space between parentheses of control flow statements</span></span><br /><br /><span data-ttu-id="737bd-409">`expressions` – inserir espaço entre os parênteses das expressões</span><span class="sxs-lookup"><span data-stu-id="737bd-409">`expressions` - Place space between parentheses of expressions</span></span><br /><br /><span data-ttu-id="737bd-410">`type_casts` – inserir espaço entre os parênteses nas conversões de tipo</span><span class="sxs-lookup"><span data-stu-id="737bd-410">`type_casts` - Place space between parentheses in type casts</span></span> |

<span data-ttu-id="737bd-411">Se você omitir essa regra ou usar um valor diferente de `control_flow_statements`, `expressions` ou `type_casts`, a configuração não será aplicada.</span><span class="sxs-lookup"><span data-stu-id="737bd-411">If you omit this rule or use a value other than `control_flow_statements`, `expressions`, or `type_casts`, the setting is not applied.</span></span>

<span data-ttu-id="737bd-412">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-412">Code examples:</span></span>

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

#### <a name="csharp_space_before_colon_in_inheritance_clause"></a><span data-ttu-id="737bd-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="737bd-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="737bd-414">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-414">Property</span></span>|<span data-ttu-id="737bd-415">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-415">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-416">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-416">**Option name**</span></span> | <span data-ttu-id="737bd-417">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="737bd-417">csharp_space_before_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="737bd-418">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-418">**Applicable languages**</span></span> | <span data-ttu-id="737bd-419">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-419">C#</span></span> |
| <span data-ttu-id="737bd-420">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-420">**Introduced version**</span></span> | <span data-ttu-id="737bd-421">Visual Studio 2017 versão 15.7</span><span class="sxs-lookup"><span data-stu-id="737bd-421">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="737bd-422">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-422">**Option values**</span></span> | <span data-ttu-id="737bd-423">`true` – remover um caractere de espaço antes dos dois-pontos para bases ou interfaces em uma declaração de tipo</span><span class="sxs-lookup"><span data-stu-id="737bd-423">`true` - Place a space character before the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="737bd-424">`false` – remover um espaço antes dos dois-pontos para bases ou interfaces em uma declaração de tipo</span><span class="sxs-lookup"><span data-stu-id="737bd-424">`false` - Remove space before the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="737bd-425">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-425">Code examples:</span></span>

```csharp
// csharp_space_before_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_before_colon_in_inheritance_clause = false
interface I
{

}

class C: I
{

}
```

#### <a name="csharp_space_after_colon_in_inheritance_clause"></a><span data-ttu-id="737bd-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="737bd-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="737bd-427">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-427">Property</span></span>|<span data-ttu-id="737bd-428">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-428">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-429">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-429">**Option name**</span></span> | <span data-ttu-id="737bd-430">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="737bd-430">csharp_space_after_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="737bd-431">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-431">**Applicable languages**</span></span> | <span data-ttu-id="737bd-432">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-432">C#</span></span> |
| <span data-ttu-id="737bd-433">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-433">**Introduced version**</span></span> | <span data-ttu-id="737bd-434">Visual Studio 2017 versão 15.7</span><span class="sxs-lookup"><span data-stu-id="737bd-434">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="737bd-435">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-435">**Option values**</span></span> | <span data-ttu-id="737bd-436">`true` – inserir um caractere de espaço após os dois-pontos para bases ou interfaces em uma declaração de tipo</span><span class="sxs-lookup"><span data-stu-id="737bd-436">`true` - Place a space character after the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="737bd-437">`false` – remover um espaço após os dois-pontos para bases ou interfaces em uma declaração de tipo</span><span class="sxs-lookup"><span data-stu-id="737bd-437">`false` - Remove space after the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="737bd-438">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-438">Code examples:</span></span>

```csharp
// csharp_space_after_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_after_colon_in_inheritance_clause = false
interface I
{

}

class C :I
{

}
```

#### <a name="csharp_space_around_binary_operators"></a><span data-ttu-id="737bd-439">csharp\_space\_around\_binary_operators</span><span class="sxs-lookup"><span data-stu-id="737bd-439">csharp\_space\_around\_binary_operators</span></span>

|<span data-ttu-id="737bd-440">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-440">Property</span></span>|<span data-ttu-id="737bd-441">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-441">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-442">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-442">**Option name**</span></span> | <span data-ttu-id="737bd-443">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="737bd-443">csharp_space_around_binary_operators</span></span> |
| <span data-ttu-id="737bd-444">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-444">**Applicable languages**</span></span> | <span data-ttu-id="737bd-445">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-445">C#</span></span> |
| <span data-ttu-id="737bd-446">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-446">**Introduced version**</span></span> | <span data-ttu-id="737bd-447">Visual Studio 2017 versão 15.7</span><span class="sxs-lookup"><span data-stu-id="737bd-447">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="737bd-448">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-448">**Option values**</span></span> | <span data-ttu-id="737bd-449">`before_and_after` – inserir espaço antes e depois do operador binário</span><span class="sxs-lookup"><span data-stu-id="737bd-449">`before_and_after` - Insert space before and after the binary operator</span></span><br /><br /><span data-ttu-id="737bd-450">`none` – remover espaços antes e depois do operador binário</span><span class="sxs-lookup"><span data-stu-id="737bd-450">`none` - Remove spaces before and after the binary operator</span></span><br /><br /><span data-ttu-id="737bd-451">`ignore` – ignorar espaços em torno de operadores binários</span><span class="sxs-lookup"><span data-stu-id="737bd-451">`ignore` - Ignore spaces around binary operators</span></span> |

<span data-ttu-id="737bd-452">Se você omitir essa regra ou usar um valor diferente de `before_and_after`, `none` ou `ignore`, a configuração não será aplicada.</span><span class="sxs-lookup"><span data-stu-id="737bd-452">If you omit this rule, or use a value other than `before_and_after`, `none`, or `ignore`, the setting is not applied.</span></span>

<span data-ttu-id="737bd-453">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-453">Code examples:</span></span>

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

#### <a name="csharp_space_between_method_declaration_parameter_list_parentheses"></a><span data-ttu-id="737bd-454">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-454">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>

|<span data-ttu-id="737bd-455">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-455">Property</span></span>|<span data-ttu-id="737bd-456">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-456">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-457">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-457">**Option name**</span></span> | <span data-ttu-id="737bd-458">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-458">csharp_space_between_method_declaration_parameter_list_parentheses</span></span> |
| <span data-ttu-id="737bd-459">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-459">**Applicable languages**</span></span> | <span data-ttu-id="737bd-460">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-460">C#</span></span> |
| <span data-ttu-id="737bd-461">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-461">**Introduced version**</span></span> | <span data-ttu-id="737bd-462">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-462">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-463">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-463">**Option values**</span></span> | <span data-ttu-id="737bd-464">`true` – posicionar um caractere de espaço após o parêntese de abertura e antes do parêntese de fechamento de uma lista de parâmetros de declaração de método</span><span class="sxs-lookup"><span data-stu-id="737bd-464">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span><br /><br /><span data-ttu-id="737bd-465">`false` – remover caracteres de espaço após o parêntese de abertura e antes do parêntese de fechamento de uma lista de parâmetros de declaração de método</span><span class="sxs-lookup"><span data-stu-id="737bd-465">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span> |

<span data-ttu-id="737bd-466">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-466">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

#### <a name="csharp_space_between_method_declaration_empty_parameter_list_parentheses"></a><span data-ttu-id="737bd-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="737bd-468">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-468">Property</span></span>|<span data-ttu-id="737bd-469">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-469">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-470">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-470">**Option name**</span></span> | <span data-ttu-id="737bd-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="737bd-472">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-472">**Applicable languages**</span></span> | <span data-ttu-id="737bd-473">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-473">C#</span></span> |
| <span data-ttu-id="737bd-474">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-474">**Introduced version**</span></span> | <span data-ttu-id="737bd-475">Visual Studio 2017 versão 15.7</span><span class="sxs-lookup"><span data-stu-id="737bd-475">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="737bd-476">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-476">**Option values**</span></span> | <span data-ttu-id="737bd-477">`true` – inserir um espaço nos parênteses vazios da lista de parâmetros para uma declaração de método</span><span class="sxs-lookup"><span data-stu-id="737bd-477">`true` - Insert space within empty parameter list parentheses for a method declaration</span></span><br /><br /><span data-ttu-id="737bd-478">`false` – remover um espaço nos parênteses vazios da lista de parâmetros para uma declaração de método</span><span class="sxs-lookup"><span data-stu-id="737bd-478">`false` - Remove space within empty parameter list parentheses for a method declaration</span></span> |

<span data-ttu-id="737bd-479">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-479">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_empty_parameter_list_parentheses = true
void Goo( )
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}

// csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_between_method_declaration_name_and_open_parenthesis"></a><span data-ttu-id="737bd-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="737bd-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>

|<span data-ttu-id="737bd-481">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-481">Property</span></span>|<span data-ttu-id="737bd-482">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-482">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-483">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-483">**Option name**</span></span> | <span data-ttu-id="737bd-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="737bd-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span> |
| <span data-ttu-id="737bd-485">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-485">**Applicable languages**</span></span> | <span data-ttu-id="737bd-486">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-486">C#</span></span> |
| <span data-ttu-id="737bd-487">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-487">**Option values**</span></span> | <span data-ttu-id="737bd-488">`true` – inserir um caractere de espaço entre o nome do método e o parêntese de abertura na declaração do método</span><span class="sxs-lookup"><span data-stu-id="737bd-488">`true` - Place a space character between the method name and opening parenthesis in the method declaration</span></span><br /><br /><span data-ttu-id="737bd-489">`false` – remover um caractere de espaço entre o nome do método e o parêntese de abertura na declaração do método</span><span class="sxs-lookup"><span data-stu-id="737bd-489">`false` - Remove space characters between the method name and opening parenthesis in the method declaration</span></span> |

<span data-ttu-id="737bd-490">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-490">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_name_and_open_parenthesis = true
void M () { }

// csharp_space_between_method_declaration_name_and_open_parenthesis = false
void M() { }
```

#### <a name="csharp_space_between_method_call_parameter_list_parentheses"></a><span data-ttu-id="737bd-491">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-491">csharp_space_between_method_call_parameter_list_parentheses</span></span>

|<span data-ttu-id="737bd-492">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-492">Property</span></span>|<span data-ttu-id="737bd-493">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-493">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-494">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-494">**Option name**</span></span> | <span data-ttu-id="737bd-495">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-495">csharp_space_between_method_call_parameter_list_parentheses</span></span> |
| <span data-ttu-id="737bd-496">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-496">**Applicable languages**</span></span> | <span data-ttu-id="737bd-497">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-497">C#</span></span> |
| <span data-ttu-id="737bd-498">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-498">**Introduced version**</span></span> | <span data-ttu-id="737bd-499">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-499">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-500">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-500">**Option values**</span></span> | <span data-ttu-id="737bd-501">`true` – posicionar um caractere de espaço após o parêntese de abertura e antes do parêntese de fechamento de uma chamada de método</span><span class="sxs-lookup"><span data-stu-id="737bd-501">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method call</span></span><br /><br /><span data-ttu-id="737bd-502">`false` – remover caracteres de espaço após o parêntese de abertura e antes do parêntese de fechamento de uma chamada de método</span><span class="sxs-lookup"><span data-stu-id="737bd-502">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method call</span></span> |

<span data-ttu-id="737bd-503">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-503">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

#### <a name="csharp_space_between_method_call_empty_parameter_list_parentheses"></a><span data-ttu-id="737bd-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="737bd-505">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-505">Property</span></span>|<span data-ttu-id="737bd-506">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-506">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-507">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-507">**Option name**</span></span> | <span data-ttu-id="737bd-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="737bd-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="737bd-509">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-509">**Applicable languages**</span></span> | <span data-ttu-id="737bd-510">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-510">C#</span></span> |
| <span data-ttu-id="737bd-511">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-511">**Introduced version**</span></span> | <span data-ttu-id="737bd-512">Visual Studio 2017 versão 15.7</span><span class="sxs-lookup"><span data-stu-id="737bd-512">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="737bd-513">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-513">**Option values**</span></span> | <span data-ttu-id="737bd-514">`true` – inserir espaço dentro dos parênteses da lista de argumentos vazia</span><span class="sxs-lookup"><span data-stu-id="737bd-514">`true` - Insert space within empty argument list parentheses</span></span><br /><br /><span data-ttu-id="737bd-515">`false` – remover espaço dentro dos parênteses da lista de argumentos vazia</span><span class="sxs-lookup"><span data-stu-id="737bd-515">`false` - Remove space within empty argument list parentheses</span></span> |

<span data-ttu-id="737bd-516">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-516">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_empty_parameter_list_parentheses = true
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo( );
}

// csharp_space_between_method_call_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_between_method_call_name_and_opening_parenthesis"></a><span data-ttu-id="737bd-517">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="737bd-517">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>

|<span data-ttu-id="737bd-518">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-518">Property</span></span>|<span data-ttu-id="737bd-519">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-519">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-520">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-520">**Option name**</span></span> | <span data-ttu-id="737bd-521">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="737bd-521">csharp_space_between_method_call_name_and_opening_parenthesis</span></span> |
| <span data-ttu-id="737bd-522">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-522">**Applicable languages**</span></span> | <span data-ttu-id="737bd-523">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-523">C#</span></span> |
| <span data-ttu-id="737bd-524">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-524">**Introduced version**</span></span> | <span data-ttu-id="737bd-525">Visual Studio 2017 versão 15.7</span><span class="sxs-lookup"><span data-stu-id="737bd-525">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="737bd-526">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-526">**Option values**</span></span> | <span data-ttu-id="737bd-527">`true` – inserir espaço entre o nome da chamada de método e o parêntese de abertura</span><span class="sxs-lookup"><span data-stu-id="737bd-527">`true` - Insert space between method call name and opening parenthesis</span></span><br /><br /><span data-ttu-id="737bd-528">`false` – remover espaço entre o nome da chamada de método e o parêntese de abertura</span><span class="sxs-lookup"><span data-stu-id="737bd-528">`false` - Remove space between method call name and opening parenthesis</span></span> |

<span data-ttu-id="737bd-529">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-529">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_name_and_opening_parenthesis = true
void Goo()
{
    Goo (1);
}

void Goo(int x)
{
    Goo ();
}

// csharp_space_between_method_call_name_and_opening_parenthesis = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_after_comma"></a><span data-ttu-id="737bd-530">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="737bd-530">csharp_space_after_comma</span></span>

|<span data-ttu-id="737bd-531">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-531">Property</span></span>|<span data-ttu-id="737bd-532">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-532">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-533">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-533">**Option name**</span></span> | <span data-ttu-id="737bd-534">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="737bd-534">csharp_space_after_comma</span></span> |
| <span data-ttu-id="737bd-535">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-535">**Applicable languages**</span></span> | <span data-ttu-id="737bd-536">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-536">C#</span></span> |
| <span data-ttu-id="737bd-537">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-537">**Option values**</span></span> | <span data-ttu-id="737bd-538">`true` – inserir espaço após uma vírgula</span><span class="sxs-lookup"><span data-stu-id="737bd-538">`true` - Insert space after a comma</span></span><br /><br /><span data-ttu-id="737bd-539">`false` – remover o espaço após uma vírgula</span><span class="sxs-lookup"><span data-stu-id="737bd-539">`false` - Remove space after a comma</span></span> |

<span data-ttu-id="737bd-540">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-540">Code examples:</span></span>

```csharp
// csharp_space_after_comma = true
int[] x = new int[] { 1, 2, 3, 4, 5 };

// csharp_space_after_comma = false
int[] x = new int[] { 1,2,3,4,5 }
```

#### <a name="csharp_space_before_comma"></a><span data-ttu-id="737bd-541">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="737bd-541">csharp_space_before_comma</span></span>

|<span data-ttu-id="737bd-542">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-542">Property</span></span>|<span data-ttu-id="737bd-543">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-543">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-544">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-544">**Option name**</span></span> | <span data-ttu-id="737bd-545">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="737bd-545">csharp_space_before_comma</span></span> |
| <span data-ttu-id="737bd-546">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-546">**Applicable languages**</span></span> | <span data-ttu-id="737bd-547">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-547">C#</span></span> |
| <span data-ttu-id="737bd-548">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-548">**Option values**</span></span> | <span data-ttu-id="737bd-549">`true` – inserir espaço antes de uma vírgula</span><span class="sxs-lookup"><span data-stu-id="737bd-549">`true` - Insert space before a comma</span></span><br /><br /><span data-ttu-id="737bd-550">`false` – remover espaço antes de uma vírgula</span><span class="sxs-lookup"><span data-stu-id="737bd-550">`false` - Remove space before a comma</span></span> |

<span data-ttu-id="737bd-551">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-551">Code examples:</span></span>

```csharp
// csharp_space_before_comma = true
int[] x = new int[] { 1 , 2 , 3 , 4 , 5 };

// csharp_space_before_comma = false
int[] x = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_after_dot"></a><span data-ttu-id="737bd-552">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="737bd-552">csharp_space_after_dot</span></span>

|<span data-ttu-id="737bd-553">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-553">Property</span></span>|<span data-ttu-id="737bd-554">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-554">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-555">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-555">**Option name**</span></span> | <span data-ttu-id="737bd-556">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="737bd-556">csharp_space_after_dot</span></span> |
| <span data-ttu-id="737bd-557">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-557">**Applicable languages**</span></span> | <span data-ttu-id="737bd-558">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-558">C#</span></span> |
| <span data-ttu-id="737bd-559">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-559">**Option values**</span></span> | <span data-ttu-id="737bd-560">`true` – inserir espaço após um ponto</span><span class="sxs-lookup"><span data-stu-id="737bd-560">`true` - Insert space after a dot</span></span><br /><br /><span data-ttu-id="737bd-561">`false` – remover o espaço após um ponto</span><span class="sxs-lookup"><span data-stu-id="737bd-561">`false` - Remove space after a dot</span></span> |

<span data-ttu-id="737bd-562">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-562">Code examples:</span></span>

```csharp
// csharp_space_after_dot = true
this. Goo();

// csharp_space_after_dot = false
this.Goo();
```

#### <a name="csharp_space_before_dot"></a><span data-ttu-id="737bd-563">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="737bd-563">csharp_space_before_dot</span></span>

|<span data-ttu-id="737bd-564">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-564">Property</span></span>|<span data-ttu-id="737bd-565">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-565">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-566">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-566">**Option name**</span></span> | <span data-ttu-id="737bd-567">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="737bd-567">csharp_space_before_dot</span></span> |
| <span data-ttu-id="737bd-568">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-568">**Applicable languages**</span></span> | <span data-ttu-id="737bd-569">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-569">C#</span></span> |
| <span data-ttu-id="737bd-570">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-570">**Option values**</span></span> | <span data-ttu-id="737bd-571">`true` – inserir espaço antes de um ponto</span><span class="sxs-lookup"><span data-stu-id="737bd-571">`true` - Insert space before a dot</span></span> <br /><br /><span data-ttu-id="737bd-572">`false` – remover espaço antes de um ponto</span><span class="sxs-lookup"><span data-stu-id="737bd-572">`false` - Remove space before a dot</span></span> |

<span data-ttu-id="737bd-573">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-573">Code examples:</span></span>

```csharp
// csharp_space_before_dot = true
this .Goo();

// csharp_space_before_dot = false
this.Goo();
```

#### <a name="csharp_space_after_semicolon_in_for_statement"></a><span data-ttu-id="737bd-574">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="737bd-574">csharp_space_after_semicolon_in_for_statement</span></span>

|<span data-ttu-id="737bd-575">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-575">Property</span></span>|<span data-ttu-id="737bd-576">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-576">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-577">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-577">**Option name**</span></span> | <span data-ttu-id="737bd-578">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="737bd-578">csharp_space_after_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="737bd-579">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-579">**Applicable languages**</span></span> | <span data-ttu-id="737bd-580">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-580">C#</span></span> |
| <span data-ttu-id="737bd-581">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-581">**Option values**</span></span> | <span data-ttu-id="737bd-582">`true` – inserir espaço após cada ponto e vírgula em uma instrução `for`</span><span class="sxs-lookup"><span data-stu-id="737bd-582">`true` - Insert space after each semicolon in a `for` statement</span></span><br /><br /><span data-ttu-id="737bd-583">`false` – remover espaço após cada ponto e vírgula em uma instrução `for`</span><span class="sxs-lookup"><span data-stu-id="737bd-583">`false` - Remove space after each semicolon in a `for` statement</span></span> |

<span data-ttu-id="737bd-584">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-584">Code examples:</span></span>

```csharp
// csharp_space_after_semicolon_in_for_statement = true
for (int i = 0; i < x.Length; i++)

// csharp_space_after_semicolon_in_for_statement = false
for (int i = 0;i < x.Length;i++)
```

##### <a name="csharp_space_before_semicolon_in_for_statement"></a><span data-ttu-id="737bd-585">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="737bd-585">csharp_space_before_semicolon_in_for_statement</span></span>

|<span data-ttu-id="737bd-586">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-586">Property</span></span>|<span data-ttu-id="737bd-587">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-587">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-588">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-588">**Option name**</span></span> | <span data-ttu-id="737bd-589">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="737bd-589">csharp_space_before_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="737bd-590">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-590">**Applicable languages**</span></span> | <span data-ttu-id="737bd-591">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-591">C#</span></span> |
| <span data-ttu-id="737bd-592">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-592">**Option values**</span></span> | <span data-ttu-id="737bd-593">`true` – inserir espaço antes de cada ponto e vírgula em uma instrução `for`</span><span class="sxs-lookup"><span data-stu-id="737bd-593">`true` - Insert space before each semicolon in a `for` statement</span></span> <br /><br /><span data-ttu-id="737bd-594">`false` – remover espaço antes de cada ponto e vírgula em uma instrução `for`</span><span class="sxs-lookup"><span data-stu-id="737bd-594">`false` - Remove space before each semicolon in a `for` statement</span></span> |

<span data-ttu-id="737bd-595">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-595">Code examples:</span></span>

```csharp
// csharp_space_before_semicolon_in_for_statement = true
for (int i = 0 ; i < x.Length ; i++)

// csharp_space_before_semicolon_in_for_statement = false
for (int i = 0; i < x.Length; i++)
```

#### <a name="csharp_space_around_declaration_statements"></a><span data-ttu-id="737bd-596">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-596">csharp_space_around_declaration_statements</span></span>

|<span data-ttu-id="737bd-597">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-597">Property</span></span>|<span data-ttu-id="737bd-598">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-598">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-599">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-599">**Option name**</span></span> | <span data-ttu-id="737bd-600">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-600">csharp_space_around_declaration_statements</span></span> |
| <span data-ttu-id="737bd-601">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-601">**Applicable languages**</span></span> | <span data-ttu-id="737bd-602">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-602">C#</span></span> |
| <span data-ttu-id="737bd-603">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-603">**Option values**</span></span> | <span data-ttu-id="737bd-604">`ignore` – não remover caracteres de espaço extra em instruções de declaração</span><span class="sxs-lookup"><span data-stu-id="737bd-604">`ignore` - Don't remove extra space characters in declaration statements</span></span><br /><br /><span data-ttu-id="737bd-605">`false` – remover caracteres de espaço extra em instruções de declaração</span><span class="sxs-lookup"><span data-stu-id="737bd-605">`false` - Remove extra space characters in declaration statements</span></span> |

<span data-ttu-id="737bd-606">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-606">Code examples:</span></span>

```csharp
// csharp_space_around_declaration_statements = ignore
int    x    =    0   ;

// csharp_space_around_declaration_statements = false
int x = 0;
```

#### <a name="csharp_space_before_open_square_brackets"></a><span data-ttu-id="737bd-607">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-607">csharp_space_before_open_square_brackets</span></span>

|<span data-ttu-id="737bd-608">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-608">Property</span></span>|<span data-ttu-id="737bd-609">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-609">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-610">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-610">**Option name**</span></span> | <span data-ttu-id="737bd-611">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-611">csharp_space_before_open_square_brackets</span></span> |
| <span data-ttu-id="737bd-612">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-612">**Applicable languages**</span></span> | <span data-ttu-id="737bd-613">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-613">C#</span></span> |
| <span data-ttu-id="737bd-614">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-614">**Option values**</span></span> | <span data-ttu-id="737bd-615">`true` – inserir espaço antes dos colchetes de abertura `[`</span><span class="sxs-lookup"><span data-stu-id="737bd-615">`true` - Insert space before opening square brackets `[`</span></span> <br /><br /><span data-ttu-id="737bd-616">`false` – remover espaço antes dos colchetes de abertura `[`</span><span class="sxs-lookup"><span data-stu-id="737bd-616">`false` - Remove space before opening square brackets `[`</span></span> |

<span data-ttu-id="737bd-617">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-617">Code examples:</span></span>

```csharp
// csharp_space_before_open_square_brackets = true
int [] numbers = new int [] { 1, 2, 3, 4, 5 };

// csharp_space_before_open_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_empty_square_brackets"></a><span data-ttu-id="737bd-618">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-618">csharp_space_between_empty_square_brackets</span></span>

|<span data-ttu-id="737bd-619">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-619">Property</span></span>|<span data-ttu-id="737bd-620">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-620">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-621">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-621">**Option name**</span></span> | <span data-ttu-id="737bd-622">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-622">csharp_space_between_empty_square_brackets</span></span> |
| <span data-ttu-id="737bd-623">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-623">**Applicable languages**</span></span> | <span data-ttu-id="737bd-624">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-624">C#</span></span> |
| <span data-ttu-id="737bd-625">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-625">**Option values**</span></span> | <span data-ttu-id="737bd-626">`true` – inserir espaço entre colchetes vazios `[ ]`</span><span class="sxs-lookup"><span data-stu-id="737bd-626">`true` - Insert space between empty square brackets `[ ]`</span></span> <br /><br /><span data-ttu-id="737bd-627">`false` – remover espaço entre colchetes vazios `[]`</span><span class="sxs-lookup"><span data-stu-id="737bd-627">`false` - Remove space between empty square brackets `[]`</span></span> |

<span data-ttu-id="737bd-628">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-628">Code examples:</span></span>

```csharp
// csharp_space_between_empty_square_brackets = true
int[ ] numbers = new int[ ] { 1, 2, 3, 4, 5 };

// csharp_space_between_empty_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_square_brackets"></a><span data-ttu-id="737bd-629">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-629">csharp_space_between_square_brackets</span></span>

|<span data-ttu-id="737bd-630">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-630">Property</span></span>|<span data-ttu-id="737bd-631">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-631">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-632">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-632">**Option name**</span></span> | <span data-ttu-id="737bd-633">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="737bd-633">csharp_space_between_square_brackets</span></span> |
| <span data-ttu-id="737bd-634">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-634">**Applicable languages**</span></span> | <span data-ttu-id="737bd-635">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-635">C#</span></span> |
| <span data-ttu-id="737bd-636">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-636">**Option values**</span></span> | <span data-ttu-id="737bd-637">`true` – inserir caracteres de espaço em colchetes não vazios `[ 0 ]`</span><span class="sxs-lookup"><span data-stu-id="737bd-637">`true` - Insert space characters in non-empty square brackets `[ 0 ]`</span></span> <br /><br /><span data-ttu-id="737bd-638">`false` – remover caracteres de espaço em colchetes não vazios `[0]`</span><span class="sxs-lookup"><span data-stu-id="737bd-638">`false` - Remove space characters in non-empty square brackets `[0]`</span></span> |

<span data-ttu-id="737bd-639">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-639">Code examples:</span></span>

```csharp
// csharp_space_between_square_brackets = true
int index = numbers[ 0 ];

// csharp_space_between_square_brackets = false
int index = numbers[0];
```

### <a name="wrap-options"></a><span data-ttu-id="737bd-640">Encapsular opções</span><span class="sxs-lookup"><span data-stu-id="737bd-640">Wrap options</span></span>

<span data-ttu-id="737bd-641">Essas regras de formatação referem-se ao uso de linhas únicas em comparação com linhas separadas para instruções e blocos de código.</span><span class="sxs-lookup"><span data-stu-id="737bd-641">These formatting rules concern the use of single lines versus separate lines for statements and code blocks.</span></span>

<span data-ttu-id="737bd-642">Exemplo de arquivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="737bd-642">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

#### <a name="csharp_preserve_single_line_statements"></a><span data-ttu-id="737bd-643">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-643">csharp_preserve_single_line_statements</span></span>

|<span data-ttu-id="737bd-644">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-644">Property</span></span>|<span data-ttu-id="737bd-645">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-645">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-646">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-646">**Option name**</span></span> | <span data-ttu-id="737bd-647">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="737bd-647">csharp_preserve_single_line_statements</span></span> |
| <span data-ttu-id="737bd-648">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-648">**Applicable languages**</span></span> | <span data-ttu-id="737bd-649">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-649">C#</span></span> |
| <span data-ttu-id="737bd-650">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-650">**Introduced version**</span></span> | <span data-ttu-id="737bd-651">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-651">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-652">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-652">**Option values**</span></span> | <span data-ttu-id="737bd-653">`true` – deixar instruções e declarações de membros na mesma linha</span><span class="sxs-lookup"><span data-stu-id="737bd-653">`true` - Leave statements and member declarations on the same line</span></span><br /><br /><span data-ttu-id="737bd-654">`false` – deixar instruções e declarações de membros em linhas diferentes</span><span class="sxs-lookup"><span data-stu-id="737bd-654">`false` - Leave statements and member declarations on different lines</span></span> |

<span data-ttu-id="737bd-655">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-655">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

#### <a name="csharp_preserve_single_line_blocks"></a><span data-ttu-id="737bd-656">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="737bd-656">csharp_preserve_single_line_blocks</span></span>

|<span data-ttu-id="737bd-657">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-657">Property</span></span>|<span data-ttu-id="737bd-658">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-658">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-659">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-659">**Option name**</span></span> | <span data-ttu-id="737bd-660">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="737bd-660">csharp_preserve_single_line_blocks</span></span> |
| <span data-ttu-id="737bd-661">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-661">**Applicable languages**</span></span> | <span data-ttu-id="737bd-662">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-662">C#</span></span> |
| <span data-ttu-id="737bd-663">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-663">**Introduced version**</span></span> | <span data-ttu-id="737bd-664">Visual Studio 2017 versão 15.3</span><span class="sxs-lookup"><span data-stu-id="737bd-664">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="737bd-665">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-665">**Option values**</span></span> | <span data-ttu-id="737bd-666">`true` – deixar bloco de códigos em uma linha única</span><span class="sxs-lookup"><span data-stu-id="737bd-666">`true` - Leave code block on single line</span></span><br /><br /><span data-ttu-id="737bd-667">`false` – deixar bloco de códigos em linhas separadas</span><span class="sxs-lookup"><span data-stu-id="737bd-667">`false` - Leave code block on separate lines</span></span> |

<span data-ttu-id="737bd-668">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-668">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

### <a name="using-directive-options"></a><span data-ttu-id="737bd-669">Usando opções de diretiva</span><span class="sxs-lookup"><span data-stu-id="737bd-669">Using directive options</span></span>

<span data-ttu-id="737bd-670">Essa regra de formatação se refere ao uso do uso de diretivas que estão sendo colocadas dentro e fora de um namespace.</span><span class="sxs-lookup"><span data-stu-id="737bd-670">This formatting rule concerns the use of using directives being placed inside versus outside a namespace.</span></span>

<span data-ttu-id="737bd-671">Exemplo de arquivo *.editorconfig*:</span><span class="sxs-lookup"><span data-stu-id="737bd-671">Example *.editorconfig* file:</span></span>

```ini
# 'using' directive preferences
[*.cs]
csharp_using_directive_placement = outside_namespace
csharp_using_directive_placement = inside_namespace
```

#### <a name="csharp_using_directive_placement"></a><span data-ttu-id="737bd-672">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="737bd-672">csharp_using_directive_placement</span></span>

|<span data-ttu-id="737bd-673">Propriedade</span><span class="sxs-lookup"><span data-stu-id="737bd-673">Property</span></span>|<span data-ttu-id="737bd-674">Valor</span><span class="sxs-lookup"><span data-stu-id="737bd-674">Value</span></span>|
|-|-|
| <span data-ttu-id="737bd-675">**Nome da opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-675">**Option name**</span></span> | <span data-ttu-id="737bd-676">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="737bd-676">csharp_using_directive_placement</span></span> |
| <span data-ttu-id="737bd-677">**Idiomas aplicáveis**</span><span class="sxs-lookup"><span data-stu-id="737bd-677">**Applicable languages**</span></span> | <span data-ttu-id="737bd-678">C#</span><span class="sxs-lookup"><span data-stu-id="737bd-678">C#</span></span> |
| <span data-ttu-id="737bd-679">**Versão introduzida**</span><span class="sxs-lookup"><span data-stu-id="737bd-679">**Introduced version**</span></span> | <span data-ttu-id="737bd-680">Visual Studio 2019 versão 16.1</span><span class="sxs-lookup"><span data-stu-id="737bd-680">Visual Studio 2019 version 16.1</span></span> |
| <span data-ttu-id="737bd-681">**Valores de opção**</span><span class="sxs-lookup"><span data-stu-id="737bd-681">**Option values**</span></span> | <span data-ttu-id="737bd-682">`outside_namespace` -Deixar de usar diretivas fora do namespace</span><span class="sxs-lookup"><span data-stu-id="737bd-682">`outside_namespace` - Leave using directives outside namespace</span></span><br /><br /><span data-ttu-id="737bd-683">`inside_namespace` -Deixar de usar diretivas dentro do namespace</span><span class="sxs-lookup"><span data-stu-id="737bd-683">`inside_namespace` - Leave using directives inside namespace</span></span> |

<span data-ttu-id="737bd-684">Exemplos de código:</span><span class="sxs-lookup"><span data-stu-id="737bd-684">Code examples:</span></span>

```csharp
// csharp_using_directive_placement = outside_namespace
using System;

namespace Conventions
{

}

// csharp_using_directive_placement = inside_namespace
namespace Conventions
{
    using System;
}
```

## <a name="see-also"></a><span data-ttu-id="737bd-685">Confira também</span><span class="sxs-lookup"><span data-stu-id="737bd-685">See also</span></span>

- [<span data-ttu-id="737bd-686">Regras de linguagem</span><span class="sxs-lookup"><span data-stu-id="737bd-686">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="737bd-687">Regras de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="737bd-687">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="737bd-688">Referência de regras de estilo de código .NET</span><span class="sxs-lookup"><span data-stu-id="737bd-688">.NET code style rules reference</span></span>](index.md)
