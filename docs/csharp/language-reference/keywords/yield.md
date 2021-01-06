---
description: Palavra-chave contextual yield – referência de C#
title: Palavra-chave contextual yield – referência de C#
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: e0efad959d5212f6c07d4c4b5344761490018a4c
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899659"
---
# <a name="yield-c-reference"></a><span data-ttu-id="a2273-103">yield (Referência de C#)</span><span class="sxs-lookup"><span data-stu-id="a2273-103">yield (C# Reference)</span></span>

<span data-ttu-id="a2273-104">Ao usar a  [palavra-chave contextual](index.md#contextual-keywords)`yield` em uma instrução, você indica que o método, o operador ou o acessador `get` em que ela é exibida é um iterador.</span><span class="sxs-lookup"><span data-stu-id="a2273-104">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="a2273-105">Usar `yield` para definir um iterador elimina a necessidade de uma classe adicional explícita (a classe que mantém o estado de uma enumeração, consulte <xref:System.Collections.Generic.IEnumerator%601> para obter um exemplo) ao implementar o padrão <xref:System.Collections.IEnumerable> e <xref:System.Collections.IEnumerator> para um tipo de coleção personalizado.</span><span class="sxs-lookup"><span data-stu-id="a2273-105">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="a2273-106">O exemplo a seguir mostra as duas formas de instrução `yield`.</span><span class="sxs-lookup"><span data-stu-id="a2273-106">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="a2273-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="a2273-107">Remarks</span></span>

<span data-ttu-id="a2273-108">Você usa uma instrução `yield return` para retornar cada elemento individualmente.</span><span class="sxs-lookup"><span data-stu-id="a2273-108">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="a2273-109">A sequência retornada de um método iterador pode ser consumida usando uma instrução [foreach](foreach-in.md) ou uma consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="a2273-109">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="a2273-110">Cada iteração do loop `foreach` chama o método iterador.</span><span class="sxs-lookup"><span data-stu-id="a2273-110">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="a2273-111">Quando uma instrução `yield return` é atingida no método iterador, `expression` é retornado e o local atual no código é retido.</span><span class="sxs-lookup"><span data-stu-id="a2273-111">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="a2273-112">A execução será reiniciada desse local na próxima vez que a função iteradora for chamada.</span><span class="sxs-lookup"><span data-stu-id="a2273-112">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="a2273-113">Você pode usar uma instrução `yield break` para terminar a iteração.</span><span class="sxs-lookup"><span data-stu-id="a2273-113">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="a2273-114">Para obter mais informações sobre iteradores, consulte [Iteradores](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="a2273-114">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="a2273-115">Métodos de iterador e acessadores get</span><span class="sxs-lookup"><span data-stu-id="a2273-115">Iterator methods and get accessors</span></span>

<span data-ttu-id="a2273-116">A declaração de um iterador deve atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="a2273-116">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="a2273-117">O tipo de retorno deve ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> ou <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="a2273-117">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="a2273-118">A declaração não pode ter nenhum parâmetro [in](in-parameter-modifier.md), [ref](ref.md)ou [out](out-parameter-modifier.md) .</span><span class="sxs-lookup"><span data-stu-id="a2273-118">The declaration can't have any [in](in-parameter-modifier.md), [ref](ref.md), or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="a2273-119">O tipo `yield` de um iterador que retorna <xref:System.Collections.IEnumerable> ou <xref:System.Collections.IEnumerator> é `object`.</span><span class="sxs-lookup"><span data-stu-id="a2273-119">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="a2273-120">Se o iterador retornar <xref:System.Collections.Generic.IEnumerable%601> ou <xref:System.Collections.Generic.IEnumerator%601>, uma conversão implícita deverá existir do tipo da expressão na instrução `yield return` para o parâmetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="a2273-120">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="a2273-121">Você não pode incluir uma instrução `yield return` ou `yield break` em:</span><span class="sxs-lookup"><span data-stu-id="a2273-121">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="a2273-122">[Expressões lambda](../operators/lambda-expressions.md) e [métodos anônimos](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a2273-122">[Lambda expressions](../operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="a2273-123">Métodos que contêm blocos inseguros.</span><span class="sxs-lookup"><span data-stu-id="a2273-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="a2273-124">Para obter mais informações, consulte [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="a2273-124">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="a2273-125">Tratamento de exceções</span><span class="sxs-lookup"><span data-stu-id="a2273-125">Exception handling</span></span>

<span data-ttu-id="a2273-126">Uma instrução `yield return` não pode estar localizada em um bloco try-catch.</span><span class="sxs-lookup"><span data-stu-id="a2273-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="a2273-127">Uma instrução `yield return` pode estar localizada no bloco try de uma instrução try-finally.</span><span class="sxs-lookup"><span data-stu-id="a2273-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="a2273-128">Uma instrução `yield break` pode estar localizada em um bloco try ou em um bloco catch, mas não em um bloco finally.</span><span class="sxs-lookup"><span data-stu-id="a2273-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="a2273-129">Se o corpo `foreach` (fora do método iterador) acionar uma exceção, um bloco `finally` no método iterador será executado.</span><span class="sxs-lookup"><span data-stu-id="a2273-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="a2273-130">Implementação técnica</span><span class="sxs-lookup"><span data-stu-id="a2273-130">Technical implementation</span></span>

<span data-ttu-id="a2273-131">O código a seguir retorna uma `IEnumerable<string>` de um método iterador e itera através de seus elementos.</span><span class="sxs-lookup"><span data-stu-id="a2273-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="a2273-132">A chamada a `MyIteratorMethod` não executa o corpo do método.</span><span class="sxs-lookup"><span data-stu-id="a2273-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="a2273-133">Em vez disso, a chamada retorna `IEnumerable<string>` na variável `elements`.</span><span class="sxs-lookup"><span data-stu-id="a2273-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="a2273-134">Em uma iteração do loop `foreach`, o método <xref:System.Collections.IEnumerator.MoveNext%2A> é chamado para `elements`.</span><span class="sxs-lookup"><span data-stu-id="a2273-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="a2273-135">Essa chamada executará o corpo de `MyIteratorMethod` até que a próxima instrução `yield return` seja atingida.</span><span class="sxs-lookup"><span data-stu-id="a2273-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="a2273-136">A expressão retornada pela instrução `yield return` determina não apenas o valor da variável `element` para o consumo do corpo do loop, mas também a propriedade <xref:System.Collections.Generic.IEnumerator%601.Current%2A> de `elements`, que é uma `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="a2273-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="a2273-137">Em cada iteração subsequente do loop `foreach`, a execução do corpo do iterador continuará de onde parou, parando novamente quando atingir uma instrução `yield return`.</span><span class="sxs-lookup"><span data-stu-id="a2273-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="a2273-138">O loop `foreach` é concluído quando o fim do método iterador ou uma instrução `yield break` é atingida.</span><span class="sxs-lookup"><span data-stu-id="a2273-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="a2273-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a2273-139">Example</span></span>

<span data-ttu-id="a2273-140">O exemplo a seguir contém uma instrução `yield return` dentro de um loop `for`.</span><span class="sxs-lookup"><span data-stu-id="a2273-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="a2273-141">Cada iteração do corpo da instrução `foreach` no método `Main` cria uma chamada à função iteradora `Power`.</span><span class="sxs-lookup"><span data-stu-id="a2273-141">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="a2273-142">Cada chamada à função iteradora prossegue para a próxima execução da instrução `yield return` que ocorre durante a próxima iteração do loop `for`.</span><span class="sxs-lookup"><span data-stu-id="a2273-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="a2273-143">O tipo de retorno do método iterador é <xref:System.Collections.IEnumerable> que é um tipo de interface de iterador.</span><span class="sxs-lookup"><span data-stu-id="a2273-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="a2273-144">Quando o método iterador é chamado, ele retorna um objeto enumerável que contém as potências de um número.</span><span class="sxs-lookup"><span data-stu-id="a2273-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="a2273-145">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a2273-145">Example</span></span>

<span data-ttu-id="a2273-146">O exemplo a seguir demonstra um acessador `get` que é um iterador.</span><span class="sxs-lookup"><span data-stu-id="a2273-146">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="a2273-147">No exemplo, cada instrução `yield return` retorna uma instância de uma classe definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="a2273-147">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="a2273-148">Especificação da linguagem C#</span><span class="sxs-lookup"><span data-stu-id="a2273-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a2273-149">Veja também</span><span class="sxs-lookup"><span data-stu-id="a2273-149">See also</span></span>

- [<span data-ttu-id="a2273-150">Referência do C#</span><span class="sxs-lookup"><span data-stu-id="a2273-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a2273-151">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="a2273-151">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a2273-152">foreach, in</span><span class="sxs-lookup"><span data-stu-id="a2273-152">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="a2273-153">Iterators</span><span class="sxs-lookup"><span data-stu-id="a2273-153">Iterators</span></span>](../../iterators.md)
