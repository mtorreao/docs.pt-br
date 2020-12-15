---
title: Como usar variáveis locais e matrizes de tipo implícito em uma expressão de consulta – guia de programação em C#
description: Use variáveis locais digitadas implicitamente em C# para que o compilador determine o tipo de uma variável local. Você deve usá-los para armazenar tipos anônimos.
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: bd68c913c6f0d410d97973fb28789218f88903b5
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512379"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a><span data-ttu-id="fe91e-104">Como usar variáveis locais e matrizes de tipo implícito em uma expressão de consulta (guia de programação C#)</span><span class="sxs-lookup"><span data-stu-id="fe91e-104">How to use implicitly typed local variables and arrays in a query expression (C# Programming Guide)</span></span>

<span data-ttu-id="fe91e-105">Será possível usar variáveis locais de tipo implícito sempre que você desejar que o compilador determine o tipo de uma variável local.</span><span class="sxs-lookup"><span data-stu-id="fe91e-105">You can use implicitly typed local variables whenever you want the compiler to determine the type of a local variable.</span></span> <span data-ttu-id="fe91e-106">É necessário usar variáveis locais de tipo implícito para armazenar tipos anônimos, usados frequentemente em expressões de consulta.</span><span class="sxs-lookup"><span data-stu-id="fe91e-106">You must use implicitly typed local variables to store anonymous types, which are often used in query expressions.</span></span> <span data-ttu-id="fe91e-107">Os exemplos a seguir ilustram usos obrigatórios e opcionais de variáveis locais de tipo implícito em consultas.</span><span class="sxs-lookup"><span data-stu-id="fe91e-107">The following examples illustrate both optional and required uses of implicitly typed local variables in queries.</span></span>  
  
 <span data-ttu-id="fe91e-108">As variáveis locais de tipo implícito são declaradas usando a palavra-chave contextual [var](../../language-reference/keywords/var.md).</span><span class="sxs-lookup"><span data-stu-id="fe91e-108">Implicitly typed local variables are declared by using the [var](../../language-reference/keywords/var.md) contextual keyword.</span></span> <span data-ttu-id="fe91e-109">Para obter mais informações, consulte [Variáveis locais de tipo implícito](./implicitly-typed-local-variables.md) e [Matrizes de tipo implícito](../arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="fe91e-109">For more information, see [Implicitly Typed Local Variables](./implicitly-typed-local-variables.md) and [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe91e-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fe91e-110">Example</span></span>  

 <span data-ttu-id="fe91e-111">O exemplo a seguir mostra um cenário comum em que a palavra-chave `var` é necessária: uma expressão de consulta que produz uma sequência de tipos anônimos.</span><span class="sxs-lookup"><span data-stu-id="fe91e-111">The following example shows a common scenario in which the `var` keyword is required: a query expression that produces a sequence of anonymous types.</span></span> <span data-ttu-id="fe91e-112">Nesse cenário, a variável de consulta e a variável de iteração na instrução `foreach` devem ser tipadas implicitamente usando `var`, porque você não tem acesso a um nome de tipo para o tipo anônimo.</span><span class="sxs-lookup"><span data-stu-id="fe91e-112">In this scenario, both the query variable and the iteration variable in the `foreach` statement must be implicitly typed by using `var` because you do not have access to a type name for the anonymous type.</span></span> <span data-ttu-id="fe91e-113">Para obter mais informações sobre tipos anônimos, consulte [Tipos anônimos](./anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="fe91e-113">For more information about anonymous types, see [Anonymous Types](./anonymous-types.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="fe91e-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fe91e-114">Example</span></span>  

 <span data-ttu-id="fe91e-115">O exemplo a seguir usa a palavra-chave `var` em uma situação semelhante, mas na qual o uso de `var` é opcional.</span><span class="sxs-lookup"><span data-stu-id="fe91e-115">The following example uses the `var` keyword in a situation that is similar, but in which the use of `var` is optional.</span></span> <span data-ttu-id="fe91e-116">Como `student.LastName` é uma cadeia de caracteres, a execução da consulta retorna uma sequência de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fe91e-116">Because `student.LastName` is a string, execution of the query returns a sequence of strings.</span></span> <span data-ttu-id="fe91e-117">Portanto, o tipo de `queryID` poderia ser declarado como `System.Collections.Generic.IEnumerable<string>` em vez de `var`.</span><span class="sxs-lookup"><span data-stu-id="fe91e-117">Therefore, the type of `queryID` could be declared as `System.Collections.Generic.IEnumerable<string>` instead of `var`.</span></span> <span data-ttu-id="fe91e-118">A palavra-chave `var` é usada por conveniência.</span><span class="sxs-lookup"><span data-stu-id="fe91e-118">Keyword `var` is used for convenience.</span></span> <span data-ttu-id="fe91e-119">No exemplo, a variável de iteração na instrução `foreach` tem tipo explícito como uma cadeia de caracteres, mas, em vez disso, poderia ser declarada usando `var`.</span><span class="sxs-lookup"><span data-stu-id="fe91e-119">In the example, the iteration variable in the `foreach` statement is explicitly typed as a string, but it could instead be declared by using `var`.</span></span> <span data-ttu-id="fe91e-120">Como o tipo da variável de iteração não é um tipo anônimo, o uso de `var` é opcional, não obrigatório.</span><span class="sxs-lookup"><span data-stu-id="fe91e-120">Because the type of the iteration variable is not an anonymous type, the use of `var` is an option, not a requirement.</span></span> <span data-ttu-id="fe91e-121">Lembre-se de que `var` por si só não é um tipo, mas uma instrução para o compilador inferir e atribuir o tipo.</span><span class="sxs-lookup"><span data-stu-id="fe91e-121">Remember, `var` itself is not a type, but an instruction to the compiler to infer and assign the type.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a><span data-ttu-id="fe91e-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fe91e-122">See also</span></span>

- [<span data-ttu-id="fe91e-123">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="fe91e-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fe91e-124">Métodos de Extensão</span><span class="sxs-lookup"><span data-stu-id="fe91e-124">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="fe91e-125">LINQ (Consulta Integrada à Linguagem)</span><span class="sxs-lookup"><span data-stu-id="fe91e-125">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="fe91e-126">var</span><span class="sxs-lookup"><span data-stu-id="fe91e-126">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="fe91e-127">LINQ em C#</span><span class="sxs-lookup"><span data-stu-id="fe91e-127">LINQ in C#</span></span>](../../linq/index.md)
