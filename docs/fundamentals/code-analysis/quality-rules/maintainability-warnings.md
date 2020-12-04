---
title: Regras de manutenção (análise de código)
description: Saiba mais sobre as regras de manutenção da análise de código.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- rules, maintainability
- managed code analysis rules, maintainability rules
- maintainability rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: fc2ef2b42eeba241b7af66b579a60365ad2b88c7
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96584726"
---
# <a name="maintainability-rules"></a><span data-ttu-id="ec674-103">Regras de facilidade de manutenção</span><span class="sxs-lookup"><span data-stu-id="ec674-103">Maintainability rules</span></span>

<span data-ttu-id="ec674-104">As regras de manutenção dão suporte à manutenção da biblioteca e do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ec674-104">Maintainability rules support library and application maintenance.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ec674-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ec674-105">In this section</span></span>

| <span data-ttu-id="ec674-106">Regra</span><span class="sxs-lookup"><span data-stu-id="ec674-106">Rule</span></span> | <span data-ttu-id="ec674-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec674-107">Description</span></span> |
|-----------|-----------------------------------|
| [<span data-ttu-id="ec674-108">CA1501: Evitar herança excessiva</span><span class="sxs-lookup"><span data-stu-id="ec674-108">CA1501: Avoid excessive inheritance</span></span>](ca1501.md) | <span data-ttu-id="ec674-109">Um tipo está mais de quatro níveis abaixo na hierarquia de herança.</span><span class="sxs-lookup"><span data-stu-id="ec674-109">A type is more than four levels deep in its inheritance hierarchy.</span></span> <span data-ttu-id="ec674-110">As hierarquias de tipo profundamente aninhado podem ser difíceis de seguir, compreender e manter.</span><span class="sxs-lookup"><span data-stu-id="ec674-110">Deeply nested type hierarchies can be difficult to follow, understand, and maintain.</span></span> |
| [<span data-ttu-id="ec674-111">CA1502: Evitar complexidade excessiva</span><span class="sxs-lookup"><span data-stu-id="ec674-111">CA1502: Avoid excessive complexity</span></span>](ca1502.md) | <span data-ttu-id="ec674-112">Esta regra mede o número de caminhos linearmente independentes por meio do método, o que é determinado pelo número e pela complexidade das ramificações condicionais.</span><span class="sxs-lookup"><span data-stu-id="ec674-112">This rule measures the number of linearly independent paths through the method, which is determined by the number and complexity of conditional branches.</span></span> |
| [<span data-ttu-id="ec674-113">CA1505: Evitar código de difícil manutenção</span><span class="sxs-lookup"><span data-stu-id="ec674-113">CA1505: Avoid unmaintainable code</span></span>](ca1505.md) | <span data-ttu-id="ec674-114">Um tipo ou um método tem um baixo valor de índice de facilidade de manutenção.</span><span class="sxs-lookup"><span data-stu-id="ec674-114">A type or method has a low maintainability index value.</span></span> <span data-ttu-id="ec674-115">Um baixo índice de facilidade de manutenção indica que um tipo ou um método é provavelmente difícil de manter e seria um bom candidato para um novo design.</span><span class="sxs-lookup"><span data-stu-id="ec674-115">A low maintainability index indicates that a type or method is probably difficult to maintain and would be a good candidate for redesign.</span></span> |
| [<span data-ttu-id="ec674-116">CA1506: Evitar acoplamento de classes excessivo</span><span class="sxs-lookup"><span data-stu-id="ec674-116">CA1506: Avoid excessive class coupling</span></span>](ca1506.md) | <span data-ttu-id="ec674-117">Esta regra mede o acoplamento de classes contando o número de referências de tipo exclusivas que um tipo ou um método contém.</span><span class="sxs-lookup"><span data-stu-id="ec674-117">This rule measures class coupling by counting the number of unique type references that a type or method contains.</span></span> |
| [<span data-ttu-id="ec674-118">CA1507: Usar nameof no lugar da cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec674-118">CA1507: Use nameof in place of string</span></span>](ca1507.md) | <span data-ttu-id="ec674-119">Um literal de cadeia de caracteres é usado como um argumento em que uma `nameof` expressão pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="ec674-119">A string literal is used as an argument where a `nameof` expression could be used.</span></span> |
| [<span data-ttu-id="ec674-120">CA1508: Evitar código condicional morto</span><span class="sxs-lookup"><span data-stu-id="ec674-120">CA1508: Avoid dead conditional code</span></span>](ca1508.md) | <span data-ttu-id="ec674-121">Um método tem código condicional que sempre é avaliado como `true` ou `false` em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="ec674-121">A method has conditional code that always evaluates to `true` or `false` at runtime.</span></span> <span data-ttu-id="ec674-122">Isso leva a um código inativo na `false` ramificação da condição.</span><span class="sxs-lookup"><span data-stu-id="ec674-122">This leads to dead code in the `false` branch of the condition.</span></span> |
| [<span data-ttu-id="ec674-123">CA1509: Entrada inválida no arquivo de configuração de métrica de código</span><span class="sxs-lookup"><span data-stu-id="ec674-123">CA1509: Invalid entry in code metrics configuration file</span></span>](ca1509.md) | <span data-ttu-id="ec674-124">As regras de métricas de código, como [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) e [CA1506](ca1506.md), forneciam um arquivo de configuração chamado `CodeMetricsConfig.txt` que tem uma entrada inválida.</span><span class="sxs-lookup"><span data-stu-id="ec674-124">Code metrics rules, such as [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) and [CA1506](ca1506.md), supplied a configuration file named `CodeMetricsConfig.txt` that has an invalid entry.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ec674-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="ec674-125">See also</span></span>

- [<span data-ttu-id="ec674-126">Meça a complexidade e a facilidade de manutenção do código gerenciado</span><span class="sxs-lookup"><span data-stu-id="ec674-126">Measure Complexity and Maintainability of Managed Code</span></span>](/visualstudio/code-quality/code-metrics-values)
