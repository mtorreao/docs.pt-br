---
description: is – Referência de C#
title: is – Referência de C#
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: d30ebfa2dc47265185a96514efbddc3e4937438c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "94982388"
---
# <a name="is-c-reference"></a><span data-ttu-id="6682f-103">is (Referência de C#)</span><span class="sxs-lookup"><span data-stu-id="6682f-103">is (C# Reference)</span></span>

<span data-ttu-id="6682f-104">O operador `is` verifica se o resultado de uma expressão é compatível com um tipo fornecido ou (a partir do C# 7.0) testa uma expressão em relação a um padrão.</span><span class="sxs-lookup"><span data-stu-id="6682f-104">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="6682f-105">Para obter informações sobre o operador de teste de tipo `is` , consulte a seção [is Operator](../operators/type-testing-and-cast.md#is-operator) do artigo [Type-Test and Cast Operators](../operators/type-testing-and-cast.md) .</span><span class="sxs-lookup"><span data-stu-id="6682f-105">For information about the type-testing `is` operator, see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="6682f-106">Correspondência de padrões com `is`</span><span class="sxs-lookup"><span data-stu-id="6682f-106">Pattern matching with `is`</span></span>

<span data-ttu-id="6682f-107">Começando com o C# 7.0, as instruções `is` e [switch](switch.md) permitem a correspondência de padrões.</span><span class="sxs-lookup"><span data-stu-id="6682f-107">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="6682f-108">A palavra-chave `is` dá suporte aos seguintes padrões:</span><span class="sxs-lookup"><span data-stu-id="6682f-108">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="6682f-109">[Tipo padrão](#type-pattern), que testa se uma expressão pode ser convertida em um tipo especificado e, se puder, converte a variável em uma variável desse tipo.</span><span class="sxs-lookup"><span data-stu-id="6682f-109">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts the variable to a variable of that type.</span></span>
- <span data-ttu-id="6682f-110">[Padrão constante](#constant-pattern), que testa se uma expressão é avaliada como um valor constante especificado.</span><span class="sxs-lookup"><span data-stu-id="6682f-110">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>
- <span data-ttu-id="6682f-111">[Padrão var](#var-pattern), uma correspondência que sempre é bem-sucedida e vincula o valor de uma expressão a uma nova variável local.</span><span class="sxs-lookup"><span data-stu-id="6682f-111">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="6682f-112">Padrão de tipo</span><span class="sxs-lookup"><span data-stu-id="6682f-112">Type pattern</span></span>

<span data-ttu-id="6682f-113">Ao usar o padrão de tipo para realizar a correspondência de padrões, `is` testa se uma expressão pode ser convertida em um tipo especificado e, caso possa, a converte em uma variável desse tipo.</span><span class="sxs-lookup"><span data-stu-id="6682f-113">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="6682f-114">Trata-se de uma extensão simples da instrução `is` que habilita a conversão e a avaliação de tipo concisas.</span><span class="sxs-lookup"><span data-stu-id="6682f-114">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="6682f-115">A forma geral do padrão de tipo `is` é:</span><span class="sxs-lookup"><span data-stu-id="6682f-115">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="6682f-116">Em que *expr* é uma expressão que é avaliada como uma instância de algum tipo, *digite* é o nome do tipo para o qual o resultado de *expr* deve ser convertido e *VarName* é o objeto para o qual o resultado de *expr* é convertido se o `is` teste for `true` .</span><span class="sxs-lookup"><span data-stu-id="6682f-116">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="6682f-117">A `is` expressão é `true` se *expr* não for `null` , e qualquer uma das condições a seguir for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="6682f-117">The `is` expression is `true` if *expr* isn't `null`, and any of the following conditions is true:</span></span>

- <span data-ttu-id="6682f-118">*expr* for uma instância do mesmo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="6682f-118">*expr* is an instance of the same type as *type*.</span></span>
- <span data-ttu-id="6682f-119">*expr* for uma instância de um tipo derivado de *type*.</span><span class="sxs-lookup"><span data-stu-id="6682f-119">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="6682f-120">Em outras palavras, o resultado de *expr* pode sofrer upcast para uma instância de *type*.</span><span class="sxs-lookup"><span data-stu-id="6682f-120">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>
- <span data-ttu-id="6682f-121">*expr* tem um tipo de tempo de compilação que é uma classe base de *type*, e *expr* tem um tipo de runtime que é *type* ou é derivado de *type*.</span><span class="sxs-lookup"><span data-stu-id="6682f-121">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="6682f-122">O *tipo de tempo de compilação* de uma variável é o tipo da variável, conforme definido em sua declaração.</span><span class="sxs-lookup"><span data-stu-id="6682f-122">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="6682f-123">O *tipo de runtime* de uma variável é o tipo da instância atribuída a essa variável.</span><span class="sxs-lookup"><span data-stu-id="6682f-123">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>
- <span data-ttu-id="6682f-124">*expr* é uma instância de um tipo que implementa a interface de *type*.</span><span class="sxs-lookup"><span data-stu-id="6682f-124">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="6682f-125">A partir do C# 7.1, *expr* pode ter um tipo de tempo de compilação definido por um parâmetro de tipo genérico e suas restrições.</span><span class="sxs-lookup"><span data-stu-id="6682f-125">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="6682f-126">Se *expr* for `true` e `is` for usado com uma instrução `if`, *varname* será atribuído somente dentro da instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="6682f-126">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="6682f-127">O escopo de *varname* é da expressão `is` até o final do bloco que envolve a instrução `if`.</span><span class="sxs-lookup"><span data-stu-id="6682f-127">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="6682f-128">O uso de *VarName* em qualquer outro local gera um erro de tempo de compilação para uso de uma variável que não foi atribuída.</span><span class="sxs-lookup"><span data-stu-id="6682f-128">Using *varname* in any other location generates a compile-time error for use of a variable that hasn't been assigned.</span></span>

<span data-ttu-id="6682f-129">O exemplo a seguir usa o padrão de tipo `is` para fornecer a implementação do método <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> de um tipo.</span><span class="sxs-lookup"><span data-stu-id="6682f-129">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="6682f-130">Sem a correspondência de padrões, esse código pode ser escrito da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="6682f-130">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="6682f-131">O uso da correspondência de padrões de tipo produz código mais compacto e legível eliminando a necessidade de testar se o resultado de uma conversão é um `null`.</span><span class="sxs-lookup"><span data-stu-id="6682f-131">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="6682f-132">O padrão de tipo `is` também produz código mais compacto ao determinar o tipo de um tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="6682f-132">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="6682f-133">O exemplo a seguir usa o padrão de tipo `is` para determinar se um objeto é uma instância de `Person` ou `Dog` antes de exibir o valor de uma propriedade adequada.</span><span class="sxs-lookup"><span data-stu-id="6682f-133">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="6682f-134">O código equivalente sem correspondência de padrões requer uma atribuição separada que inclui uma conversão explícita.</span><span class="sxs-lookup"><span data-stu-id="6682f-134">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="6682f-135">Padrão de constante</span><span class="sxs-lookup"><span data-stu-id="6682f-135">Constant pattern</span></span>

<span data-ttu-id="6682f-136">Ao executar a correspondência de padrões com o padrão constante, `is` testa se uma expressão é igual a uma constante especificada.</span><span class="sxs-lookup"><span data-stu-id="6682f-136">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="6682f-137">No C# 6 e em versões anteriores, o padrão constante tem suporte da instrução [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="6682f-137">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="6682f-138">A partir do C# 7.0, ele também é compatível com a instrução `is`.</span><span class="sxs-lookup"><span data-stu-id="6682f-138">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="6682f-139">Sua sintaxe é:</span><span class="sxs-lookup"><span data-stu-id="6682f-139">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="6682f-140">em que *expr* é a expressão a ser avaliada e *constant* é o valor a ser testado.</span><span class="sxs-lookup"><span data-stu-id="6682f-140">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="6682f-141">*constant* pode ser qualquer uma das expressões de constante a seguir:</span><span class="sxs-lookup"><span data-stu-id="6682f-141">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="6682f-142">Um valor literal.</span><span class="sxs-lookup"><span data-stu-id="6682f-142">A literal value.</span></span>

- <span data-ttu-id="6682f-143">O nome de uma variável `const` declarada.</span><span class="sxs-lookup"><span data-stu-id="6682f-143">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="6682f-144">Uma constante de enumeração.</span><span class="sxs-lookup"><span data-stu-id="6682f-144">An enumeration constant.</span></span>

<span data-ttu-id="6682f-145">A expressão de constante é avaliada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="6682f-145">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="6682f-146">Se *expr* e *constant* forem tipos integrais, o operador de igualdade de C# determinará se a expressão retorna `true` (ou seja, se `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="6682f-146">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="6682f-147">Caso contrário, o valor da expressão será determinado por uma chamada ao método estático [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="6682f-147">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="6682f-148">O exemplo a seguir combina os padrões de tipo e constante para testar se um objeto é uma instância de `Dice` e, caso seja, para determinar se o valor de uma distribuição de dados é 6.</span><span class="sxs-lookup"><span data-stu-id="6682f-148">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="6682f-149">É possível verificar em busca de `null` usando o padrão de constante.</span><span class="sxs-lookup"><span data-stu-id="6682f-149">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="6682f-150">A palavra-chave `null` é compatível com a instrução `is`.</span><span class="sxs-lookup"><span data-stu-id="6682f-150">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="6682f-151">Sua sintaxe é:</span><span class="sxs-lookup"><span data-stu-id="6682f-151">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="6682f-152">O exemplo a seguir demonstra uma comparação de verificações de `null`:</span><span class="sxs-lookup"><span data-stu-id="6682f-152">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

<span data-ttu-id="6682f-153">A expressão `x is null` é computada de forma diferente para tipos de referência e tipos de valor anulável.</span><span class="sxs-lookup"><span data-stu-id="6682f-153">The expression `x is null` is computed differently for reference types and nullable value types.</span></span> <span data-ttu-id="6682f-154">Para tipos de valor anulável, ele usa <xref:System.Nullable%601.HasValue?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6682f-154">For nullable value types, it uses <xref:System.Nullable%601.HasValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6682f-155">Para tipos de referência, ele usa `(object)x == null` .</span><span class="sxs-lookup"><span data-stu-id="6682f-155">For reference types, it uses `(object)x == null`.</span></span>

### <a name="var-pattern"></a><span data-ttu-id="6682f-156">Padrão var</span><span class="sxs-lookup"><span data-stu-id="6682f-156">var pattern</span></span>

<span data-ttu-id="6682f-157">Uma correspondência de padrões com o `var` padrão sempre é realizada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="6682f-157">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="6682f-158">Sua sintaxe é:</span><span class="sxs-lookup"><span data-stu-id="6682f-158">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="6682f-159">Em que o valor de *expr* sempre é atribuído a uma variável local chamada *VarName*.</span><span class="sxs-lookup"><span data-stu-id="6682f-159">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="6682f-160">*VarName* é uma variável do mesmo tipo que o tipo de *expr* de tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="6682f-160">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="6682f-161">Se *expr* for avaliada como `null` , a `is` expressão produz `true` e atribui `null` a *VarName*.</span><span class="sxs-lookup"><span data-stu-id="6682f-161">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="6682f-162">O padrão var é um dos poucos usos `is` que produz `true` para um `null` valor.</span><span class="sxs-lookup"><span data-stu-id="6682f-162">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="6682f-163">Você pode usar o `var` padrão para criar uma variável temporária dentro de uma expressão booliana, como mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="6682f-163">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="6682f-164">No exemplo anterior, a variável temporária é usada para armazenar o resultado de uma operação cara.</span><span class="sxs-lookup"><span data-stu-id="6682f-164">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="6682f-165">A variável pode ser usada várias vezes.</span><span class="sxs-lookup"><span data-stu-id="6682f-165">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6682f-166">Especificação da linguagem C#</span><span class="sxs-lookup"><span data-stu-id="6682f-166">C# language specification</span></span>
  
<span data-ttu-id="6682f-167">Para saber mais, confira a seção [O operador is](~/_csharplang/spec/expressions.md#the-is-operator) da [especificação da linguagem C#](~/_csharplang/spec/introduction.md) e as seguintes propostas da linguagem C#:</span><span class="sxs-lookup"><span data-stu-id="6682f-167">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="6682f-168">Correspondência de padrões</span><span class="sxs-lookup"><span data-stu-id="6682f-168">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="6682f-169">Correspondência de padrões com genéricos</span><span class="sxs-lookup"><span data-stu-id="6682f-169">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="6682f-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="6682f-170">See also</span></span>

- [<span data-ttu-id="6682f-171">Referência de C#</span><span class="sxs-lookup"><span data-stu-id="6682f-171">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6682f-172">Palavras-chave do C#</span><span class="sxs-lookup"><span data-stu-id="6682f-172">C# keywords</span></span>](index.md)
- [<span data-ttu-id="6682f-173">Operadores cast e teste de tipo</span><span class="sxs-lookup"><span data-stu-id="6682f-173">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
