---
description: '! operador (NULL-tolerante)-referência C#'
title: '! operador (NULL-tolerante)-referência C#'
ms.date: 11/13/2020
f1_keywords:
- nullForgiving_CSharpKeyword
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 5489c77fa7290bdd1c03e04d8cc777ab772fdce7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699624"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="5bbe3-105">!</span><span class="sxs-lookup"><span data-stu-id="5bbe3-105">!</span></span> <span data-ttu-id="5bbe3-106">operador (NULL-tolerante) (referência C#)</span><span class="sxs-lookup"><span data-stu-id="5bbe3-106">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="5bbe3-107">Disponível em C# 8,0 e posterior, o operador de sufixo unário `!` é o operador NULL-tolerante.</span><span class="sxs-lookup"><span data-stu-id="5bbe3-107">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="5bbe3-108">Em um [contexto de anotação anulável](../../nullable-references.md#nullable-annotation-context)habilitado, você usa o operador NULL-tolerante para declarar que a expressão `x` de um tipo de referência não é `null` : `x!` .</span><span class="sxs-lookup"><span data-stu-id="5bbe3-108">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="5bbe3-109">O operador de prefixo unário `!` é o [operador lógico de negação](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="5bbe3-109">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="5bbe3-110">O operador NULL-tolerante não tem nenhum efeito no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="5bbe3-110">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="5bbe3-111">Ele afeta apenas a análise de fluxo estático do compilador, alterando o estado nulo da expressão.</span><span class="sxs-lookup"><span data-stu-id="5bbe3-111">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="5bbe3-112">Em tempo de execução, `x!` a expressão é avaliada como o resultado da expressão subjacente `x` .</span><span class="sxs-lookup"><span data-stu-id="5bbe3-112">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="5bbe3-113">Para obter mais informações sobre o recurso de tipos de referência anulável, consulte [tipos de referência anuláveis](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="5bbe3-113">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="5bbe3-114">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5bbe3-114">Examples</span></span>

<span data-ttu-id="5bbe3-115">Um dos casos de uso do operador NULL-tolerante está no teste da lógica de validação de argumento.</span><span class="sxs-lookup"><span data-stu-id="5bbe3-115">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="5bbe3-116">Por exemplo, considere a seguinte classe:</span><span class="sxs-lookup"><span data-stu-id="5bbe3-116">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="5bbe3-117">Usando a [estrutura de teste MSTest](../../../core/testing/unit-testing-with-mstest.md), você pode criar o seguinte teste para a lógica de validação no construtor:</span><span class="sxs-lookup"><span data-stu-id="5bbe3-117">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="5bbe3-118">Sem o operador NULL-tolerante, o compilador gera o seguinte aviso para o código anterior: `Warning CS8625: Cannot convert null literal to non-nullable reference type` .</span><span class="sxs-lookup"><span data-stu-id="5bbe3-118">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="5bbe3-119">Usando o operador NULL-tolerante, você informa ao compilador que a passagem `null` é esperada e não deve ser avisado sobre.</span><span class="sxs-lookup"><span data-stu-id="5bbe3-119">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="5bbe3-120">Você também pode usar o operador NULL-tolerante quando sabe definitivamente que uma expressão não pode ser `null` , mas o compilador não gerencia para reconhecê-la.</span><span class="sxs-lookup"><span data-stu-id="5bbe3-120">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="5bbe3-121">No exemplo a seguir, se o `IsValid` método retornar `true` , seu argumento não será `null` e você poderá desreferenciá-lo com segurança:</span><span class="sxs-lookup"><span data-stu-id="5bbe3-121">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="5bbe3-122">Sem o operador NULL-tolerante, o compilador gera o seguinte aviso para o `p.Name` código: `Warning CS8602: Dereference of a possibly null reference` .</span><span class="sxs-lookup"><span data-stu-id="5bbe3-122">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="5bbe3-123">Se você puder modificar o `IsValid` método, poderá usar o atributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) para informar ao compilador que um argumento do `IsValid` método não pode ser `null` quando o método retornar `true` :</span><span class="sxs-lookup"><span data-stu-id="5bbe3-123">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="5bbe3-124">No exemplo anterior, você não precisa usar o operador NULL-tolerante porque o compilador tem informações suficientes para descobrir que `p` não podem estar `null` dentro da `if` instrução.</span><span class="sxs-lookup"><span data-stu-id="5bbe3-124">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="5bbe3-125">Para obter mais informações sobre os atributos que permitem fornecer informações adicionais sobre o estado nulo de uma variável, consulte [Atualizar APIs com atributos para definir expectativas nulas](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="5bbe3-125">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5bbe3-126">Especificação da linguagem C#</span><span class="sxs-lookup"><span data-stu-id="5bbe3-126">C# language specification</span></span>

<span data-ttu-id="5bbe3-127">Para obter mais informações, consulte [a seção operador NULL-tolerante](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md#the-null-forgiving-operator) do [rascunho da especificação de tipos de referência anulável](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="5bbe3-127">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5bbe3-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="5bbe3-128">See also</span></span>

- [<span data-ttu-id="5bbe3-129">Referência de C#</span><span class="sxs-lookup"><span data-stu-id="5bbe3-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5bbe3-130">Operadores e expressões C#</span><span class="sxs-lookup"><span data-stu-id="5bbe3-130">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="5bbe3-131">Tutorial: design com tipos de referência anuláveis</span><span class="sxs-lookup"><span data-stu-id="5bbe3-131">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
