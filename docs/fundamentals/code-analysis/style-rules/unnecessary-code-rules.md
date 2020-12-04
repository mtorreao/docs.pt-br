---
title: Regras de código desnecessárias
description: Saiba mais sobre regras de código desnecessárias da análise de código
ms.date: 09/30/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 16c4ba0e4bee2388736bf9813a3e8290d8d4da32
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "96585549"
---
# <a name="unnecessary-code-rules"></a><span data-ttu-id="e97ad-103">Regras de código desnecessárias</span><span class="sxs-lookup"><span data-stu-id="e97ad-103">Unnecessary code rules</span></span>

<span data-ttu-id="e97ad-104">Regras de código desnecessárias identificam diferentes partes da base de código desnecessárias e podem ser Refatorada ou removidas.</span><span class="sxs-lookup"><span data-stu-id="e97ad-104">Unnecessary code rules identify different parts of the code base that are unnecessary and can be refactored or removed.</span></span> <span data-ttu-id="e97ad-105">A presença de código desnecessário indica um ou mais dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="e97ad-105">The presence of unnecessary code indicates one of more of the following problems:</span></span>

- <span data-ttu-id="e97ad-106">Legibilidade: código que está degradando desnecessariamente a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="e97ad-106">Readability: Code that is unnecessarily degrading readability.</span></span> <span data-ttu-id="e97ad-107">Por exemplo, [IDE0001](ide0001.md) sinaliza qualificações de nome de tipo desnecessárias.</span><span class="sxs-lookup"><span data-stu-id="e97ad-107">For example, [IDE0001](ide0001.md) flags unnecessary type-name qualifications.</span></span>
- <span data-ttu-id="e97ad-108">Facilidade de manutenção: código que não é mais usado após a refatoração e que está sendo mantido desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="e97ad-108">Maintainability: Code that is no longer used after refactoring and is unnecessarily being maintained.</span></span> <span data-ttu-id="e97ad-109">Por exemplo, [IDE0051](ide0051.md) sinaliza campos particulares não utilizados, propriedades, eventos e métodos.</span><span class="sxs-lookup"><span data-stu-id="e97ad-109">For example, [IDE0051](ide0051.md) flags unused private fields, properties, events, and methods.</span></span>
- <span data-ttu-id="e97ad-110">Desempenho: computação desnecessária que não tem efeitos colaterais e leva à sobrecarga de desempenho desnecessária.</span><span class="sxs-lookup"><span data-stu-id="e97ad-110">Performance: Unnecessary computation that has no side effects and leads to unnecessary performance overhead.</span></span> <span data-ttu-id="e97ad-111">Por exemplo, [IDE0059](ide0059.md) sinaliza as atribuições de valor não utilizado em que a expressão para computar um valor não tem efeitos colaterais.</span><span class="sxs-lookup"><span data-stu-id="e97ad-111">For example, [IDE0059](ide0059.md) flags unused value assignments where the expression to compute a value has no side effects.</span></span>
- <span data-ttu-id="e97ad-112">Funcionalidade: problema funcional no código que leva ao código necessário sendo processado redundante.</span><span class="sxs-lookup"><span data-stu-id="e97ad-112">Functionality: Functional issue in code leading to required code being rendered redundant.</span></span> <span data-ttu-id="e97ad-113">Por exemplo, [IDE0060](ide0060.md) sinaliza parâmetros não utilizados em que o método ignora acidentalmente um parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="e97ad-113">For example, [IDE0060](ide0060.md) flags unused parameters where the method accidentally ignores an input parameter.</span></span>

<span data-ttu-id="e97ad-114">As regras nesta seção se preocupam com as seguintes regras de código desnecessárias:</span><span class="sxs-lookup"><span data-stu-id="e97ad-114">The rules in this section concern the following unnecessary code rules:</span></span>

- [<span data-ttu-id="e97ad-115">Simplificar o nome (IDE0001)</span><span class="sxs-lookup"><span data-stu-id="e97ad-115">Simplify name (IDE0001)</span></span>](ide0001.md)
- [<span data-ttu-id="e97ad-116">Simplificar o acesso de membro (IDE0002)</span><span class="sxs-lookup"><span data-stu-id="e97ad-116">Simplify member access (IDE0002)</span></span>](ide0002.md)
- [<span data-ttu-id="e97ad-117">Remover conversão desnecessária (IDE0004)</span><span class="sxs-lookup"><span data-stu-id="e97ad-117">Remove unnecessary cast (IDE0004)</span></span>](ide0004.md)
- [<span data-ttu-id="e97ad-118">Remover importação desnecessária (IDE0005)</span><span class="sxs-lookup"><span data-stu-id="e97ad-118">Remove unnecessary import (IDE0005)</span></span>](ide0005.md)
- [<span data-ttu-id="e97ad-119">Remover código inacessível (IDE0035)</span><span class="sxs-lookup"><span data-stu-id="e97ad-119">Remove unreachable code (IDE0035)</span></span>](ide0035.md)
- [<span data-ttu-id="e97ad-120">Remover membro privado não utilizado (IDE0051)</span><span class="sxs-lookup"><span data-stu-id="e97ad-120">Remove unused private member (IDE0051)</span></span>](ide0051.md)
- [<span data-ttu-id="e97ad-121">Remover membro privado não lido (IDE0052)</span><span class="sxs-lookup"><span data-stu-id="e97ad-121">Remove unread private member (IDE0052)</span></span>](ide0052.md)
- [<span data-ttu-id="e97ad-122">Remover valor de expressão não utilizado (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="e97ad-122">Remove unused expression value (IDE0058)</span></span>](ide0058.md)
- [<span data-ttu-id="e97ad-123">Remover atribuição de valor desnecessário (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="e97ad-123">Remove unnecessary value assignment (IDE0059)</span></span>](ide0059.md)
- [<span data-ttu-id="e97ad-124">Remover parâmetro não utilizado (IDE0060)</span><span class="sxs-lookup"><span data-stu-id="e97ad-124">Remove unused parameter (IDE0060)</span></span>](ide0060.md)
- [<span data-ttu-id="e97ad-125">Remover supressão desnecessária (IDE0079)</span><span class="sxs-lookup"><span data-stu-id="e97ad-125">Remove unnecessary suppression (IDE0079)</span></span>](ide0079.md)
- <span data-ttu-id="e97ad-126">[Remover IDE0080 (operador de supressão desnecessária)](ide0080.md) -somente C#.</span><span class="sxs-lookup"><span data-stu-id="e97ad-126">[Remove unnecessary suppression operator (IDE0080)](ide0080.md) - C# only.</span></span>
- <span data-ttu-id="e97ad-127">[Remover ' ByVal ' (IDE0081)](ide0081.md) -somente Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e97ad-127">[Remove 'ByVal' (IDE0081)](ide0081.md) - Visual Basic only.</span></span>
- [<span data-ttu-id="e97ad-128">Remover operador de igualdade desnecessária (IDE0100)</span><span class="sxs-lookup"><span data-stu-id="e97ad-128">Remove unnecessary equality operator (IDE0100)</span></span>](ide0100.md)
- <span data-ttu-id="e97ad-129">[Remover descarte desnecessário (IDE0110)](ide0110.md) -somente C#.</span><span class="sxs-lookup"><span data-stu-id="e97ad-129">[Remove unnecessary discard (IDE0110)](ide0110.md) - C# only.</span></span>

<span data-ttu-id="e97ad-130">Algumas dessas regras têm opções para configurar o comportamento da regra:</span><span class="sxs-lookup"><span data-stu-id="e97ad-130">Some of these rules have options to configure the rule behavior:</span></span>

- [<span data-ttu-id="e97ad-131">csharp_style_unused_value_expression_statement_preference (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="e97ad-131">csharp_style_unused_value_expression_statement_preference (IDE0058)</span></span>](ide0058.md#csharp_style_unused_value_expression_statement_preference)
- [<span data-ttu-id="e97ad-132">visual_basic_style_unused_value_expression_statement_preference (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="e97ad-132">visual_basic_style_unused_value_expression_statement_preference (IDE0058)</span></span>](ide0058.md#visual_basic_style_unused_value_expression_statement_preference)
- [<span data-ttu-id="e97ad-133">csharp_style_unused_value_assignment_preference (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="e97ad-133">csharp_style_unused_value_assignment_preference (IDE0059)</span></span>](ide0059.md#csharp_style_unused_value_assignment_preference)
- [<span data-ttu-id="e97ad-134">visual_basic_style_unused_value_assignment_preference (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="e97ad-134">visual_basic_style_unused_value_assignment_preference (IDE0059)</span></span>](ide0059.md#visual_basic_style_unused_value_assignment_preference)
- [<span data-ttu-id="e97ad-135">dotnet_code_quality_unused_parameters (IDE0060)</span><span class="sxs-lookup"><span data-stu-id="e97ad-135">dotnet_code_quality_unused_parameters (IDE0060)</span></span>](ide0060.md#dotnet_code_quality_unused_parameters)
- [<span data-ttu-id="e97ad-136">dotnet_remove_unnecessary_suppression_exclusions (IDE0079)</span><span class="sxs-lookup"><span data-stu-id="e97ad-136">dotnet_remove_unnecessary_suppression_exclusions (IDE0079)</span></span>](ide0079.md#dotnet_remove_unnecessary_suppression_exclusions)

## <a name="see-also"></a><span data-ttu-id="e97ad-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="e97ad-137">See also</span></span>

- [<span data-ttu-id="e97ad-138">Regras de linguagem de estilo de código</span><span class="sxs-lookup"><span data-stu-id="e97ad-138">Code style language rules</span></span>](language-rules.md)
- [<span data-ttu-id="e97ad-139">Referência de regras de estilo de código</span><span class="sxs-lookup"><span data-stu-id="e97ad-139">Code style rules reference</span></span>](index.md)
