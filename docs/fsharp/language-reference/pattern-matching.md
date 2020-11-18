---
title: Correspondência padrão
description: 'Saiba como os padrões são usados em F # para comparar dados com estruturas lógicas, decompor dados em partes constituintes ou extrair informações de dados.'
ms.date: 11/12/2020
ms.openlocfilehash: e167712b082b7f587e41a78edcaf0a0db9c7294b
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687799"
---
# <a name="pattern-matching"></a><span data-ttu-id="b9466-103">Correspondência padrão</span><span class="sxs-lookup"><span data-stu-id="b9466-103">Pattern Matching</span></span>

<span data-ttu-id="b9466-104">Padrões são regras para transformar dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="b9466-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="b9466-105">Eles são usados em toda a linguagem F # para comparar dados com uma estrutura lógica ou estruturas, decompor dados em partes constituintes ou extrair informações de dados de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="b9466-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9466-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="b9466-106">Remarks</span></span>

<span data-ttu-id="b9466-107">Padrões são usados em muitas construções de linguagem, como a `match` expressão.</span><span class="sxs-lookup"><span data-stu-id="b9466-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="b9466-108">Eles são usados quando você está processando argumentos para funções em `let` associações, expressões lambda e nos manipuladores de exceção associados à `try...with` expressão.</span><span class="sxs-lookup"><span data-stu-id="b9466-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="b9466-109">Para obter mais informações, consulte [corresponder expressões](match-expressions.md), [permitir associações](./functions/let-bindings.md), [expressões lambda: a `fun` palavra-chave](./functions/lambda-expressions-the-fun-keyword.md)e [exceções: a `try...with` expressão](./exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b9466-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](./functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="b9466-110">Por exemplo, na `match` expressão, o *padrão* é o que segue o símbolo de pipe.</span><span class="sxs-lookup"><span data-stu-id="b9466-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="b9466-111">Cada padrão atua como uma regra para transformar a entrada de alguma maneira.</span><span class="sxs-lookup"><span data-stu-id="b9466-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="b9466-112">Na `match` expressão, cada padrão é examinado, por sua vez, para ver se os dados de entrada são compatíveis com o padrão.</span><span class="sxs-lookup"><span data-stu-id="b9466-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="b9466-113">Se uma correspondência for encontrada, a expressão de resultado será executada.</span><span class="sxs-lookup"><span data-stu-id="b9466-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="b9466-114">Se uma correspondência não for encontrada, a próxima regra de padrão será testada.</span><span class="sxs-lookup"><span data-stu-id="b9466-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="b9466-115">A parte de *condição* opcional quando é explicada em [expressões de correspondência](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b9466-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="b9466-116">Os padrões com suporte são mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b9466-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="b9466-117">Em tempo de execução, a entrada é testada em relação a cada um dos seguintes padrões na ordem listada na tabela, e os padrões são aplicados recursivamente, de primeiro até o último, conforme aparecem no seu código e da esquerda para a direita para os padrões em cada linha.</span><span class="sxs-lookup"><span data-stu-id="b9466-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="b9466-118">Name</span><span class="sxs-lookup"><span data-stu-id="b9466-118">Name</span></span>|<span data-ttu-id="b9466-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="b9466-119">Description</span></span>|<span data-ttu-id="b9466-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b9466-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="b9466-121">Padrão de constante</span><span class="sxs-lookup"><span data-stu-id="b9466-121">Constant pattern</span></span>|<span data-ttu-id="b9466-122">Qualquer literal numérico, de caractere ou de cadeia de caracteres, uma constante de enumeração ou um identificador literal definido</span><span class="sxs-lookup"><span data-stu-id="b9466-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="b9466-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="b9466-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="b9466-124">Padrão de identificador</span><span class="sxs-lookup"><span data-stu-id="b9466-124">Identifier pattern</span></span>|<span data-ttu-id="b9466-125">Um valor de case de uma união discriminada, um rótulo de exceção ou um caso de padrão ativo</span><span class="sxs-lookup"><span data-stu-id="b9466-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="b9466-126">Padrão de variável</span><span class="sxs-lookup"><span data-stu-id="b9466-126">Variable pattern</span></span>|<span data-ttu-id="b9466-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="b9466-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="b9466-128">`as` padrão</span><span class="sxs-lookup"><span data-stu-id="b9466-128">`as` pattern</span></span>|<span data-ttu-id="b9466-129">*padrão* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="b9466-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="b9466-130">OU padrão</span><span class="sxs-lookup"><span data-stu-id="b9466-130">OR pattern</span></span>|<span data-ttu-id="b9466-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="b9466-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="b9466-132">E padrão</span><span class="sxs-lookup"><span data-stu-id="b9466-132">AND pattern</span></span>|<span data-ttu-id="b9466-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="b9466-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="b9466-134">Padrão de contras</span><span class="sxs-lookup"><span data-stu-id="b9466-134">Cons pattern</span></span>|<span data-ttu-id="b9466-135">*identificador* :: *lista-identificador*</span><span class="sxs-lookup"><span data-stu-id="b9466-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="b9466-136">Padrão de lista</span><span class="sxs-lookup"><span data-stu-id="b9466-136">List pattern</span></span>|<span data-ttu-id="b9466-137">[ *pattern_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="b9466-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="b9466-138">Padrão de matriz</span><span class="sxs-lookup"><span data-stu-id="b9466-138">Array pattern</span></span>|<span data-ttu-id="b9466-139">[&#124; *pattern_1*;..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="b9466-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="b9466-140">Padrão entre parênteses</span><span class="sxs-lookup"><span data-stu-id="b9466-140">Parenthesized pattern</span></span>|<span data-ttu-id="b9466-141">( *padrão* )</span><span class="sxs-lookup"><span data-stu-id="b9466-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="b9466-142">Padrão de tupla</span><span class="sxs-lookup"><span data-stu-id="b9466-142">Tuple pattern</span></span>|<span data-ttu-id="b9466-143">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="b9466-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="b9466-144">Padrão de registro</span><span class="sxs-lookup"><span data-stu-id="b9466-144">Record pattern</span></span>|<span data-ttu-id="b9466-145">{ *identifier1*  =  *pattern_1*; ... ; *identifier_n*  =  *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="b9466-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="b9466-146">Padrão de curinga</span><span class="sxs-lookup"><span data-stu-id="b9466-146">Wildcard pattern</span></span>|<span data-ttu-id="b9466-147">_</span><span class="sxs-lookup"><span data-stu-id="b9466-147">_</span></span>|`_`|
|<span data-ttu-id="b9466-148">Padrão junto com a anotação de tipo</span><span class="sxs-lookup"><span data-stu-id="b9466-148">Pattern together with type annotation</span></span>|<span data-ttu-id="b9466-149">*padrão* : *tipo*</span><span class="sxs-lookup"><span data-stu-id="b9466-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="b9466-150">Padrão de teste de tipo</span><span class="sxs-lookup"><span data-stu-id="b9466-150">Type test pattern</span></span>|<span data-ttu-id="b9466-151">:?</span><span class="sxs-lookup"><span data-stu-id="b9466-151">:?</span></span> <span data-ttu-id="b9466-152">*tipo* [como *identificador* ]</span><span class="sxs-lookup"><span data-stu-id="b9466-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="b9466-153">Padrão nulo</span><span class="sxs-lookup"><span data-stu-id="b9466-153">Null pattern</span></span>|<span data-ttu-id="b9466-154">null</span><span class="sxs-lookup"><span data-stu-id="b9466-154">null</span></span>|`null`|
|<span data-ttu-id="b9466-155">Padrão nameof</span><span class="sxs-lookup"><span data-stu-id="b9466-155">Nameof pattern</span></span>|<span data-ttu-id="b9466-156">*expr nameof*</span><span class="sxs-lookup"><span data-stu-id="b9466-156">*nameof expr*</span></span>|`nameof str`|

## <a name="constant-patterns"></a><span data-ttu-id="b9466-157">Padrões constantes</span><span class="sxs-lookup"><span data-stu-id="b9466-157">Constant Patterns</span></span>

<span data-ttu-id="b9466-158">Os padrões constantes são numéricos, caracteres e literais de cadeia de caracteres, constantes de enumeração (com o nome do tipo de enumeração incluído).</span><span class="sxs-lookup"><span data-stu-id="b9466-158">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="b9466-159">Uma `match` expressão que tem apenas padrões constantes pode ser comparada a uma instrução Case em outras linguagens.</span><span class="sxs-lookup"><span data-stu-id="b9466-159">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="b9466-160">A entrada é comparada com o valor literal e o padrão corresponde se os valores são iguais.</span><span class="sxs-lookup"><span data-stu-id="b9466-160">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="b9466-161">O tipo do literal deve ser compatível com o tipo de entrada.</span><span class="sxs-lookup"><span data-stu-id="b9466-161">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="b9466-162">O exemplo a seguir demonstra o uso de padrões literais e também usa um padrão variável e um padrão ou.</span><span class="sxs-lookup"><span data-stu-id="b9466-162">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="b9466-163">Outro exemplo de um padrão literal é um padrão baseado em constantes de enumeração.</span><span class="sxs-lookup"><span data-stu-id="b9466-163">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="b9466-164">Você deve especificar o nome do tipo de enumeração ao usar constantes de enumeração.</span><span class="sxs-lookup"><span data-stu-id="b9466-164">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="b9466-165">Padrões de identificador</span><span class="sxs-lookup"><span data-stu-id="b9466-165">Identifier Patterns</span></span>

<span data-ttu-id="b9466-166">Se o padrão for uma cadeia de caracteres que forma um identificador válido, a forma do identificador determinará como o padrão é correspondido.</span><span class="sxs-lookup"><span data-stu-id="b9466-166">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="b9466-167">Se o identificador for maior que um único caractere e começar com um caractere maiúsculo, o compilador tentará fazer uma correspondência com o padrão de identificador.</span><span class="sxs-lookup"><span data-stu-id="b9466-167">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="b9466-168">O identificador desse padrão pode ser um valor marcado com o atributo literal, um caso união discriminado, um identificador de exceção ou um caso de padrão ativo.</span><span class="sxs-lookup"><span data-stu-id="b9466-168">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="b9466-169">Se nenhum identificador correspondente for encontrado, a correspondência falhará e a próxima regra de padrão, o padrão variável, será comparada com a entrada.</span><span class="sxs-lookup"><span data-stu-id="b9466-169">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="b9466-170">Os padrões de União discriminados podem ser casos nomeados simples ou podem ter um valor, ou uma tupla contendo vários valores.</span><span class="sxs-lookup"><span data-stu-id="b9466-170">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="b9466-171">Se houver um valor, você deverá especificar um identificador para o valor.</span><span class="sxs-lookup"><span data-stu-id="b9466-171">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="b9466-172">No caso de uma tupla, você deve fornecer um padrão de tupla com um identificador para cada elemento da tupla ou um identificador com um nome de campo para um ou mais campos de União nomeados.</span><span class="sxs-lookup"><span data-stu-id="b9466-172">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="b9466-173">Consulte os exemplos de código nesta seção para obter exemplos.</span><span class="sxs-lookup"><span data-stu-id="b9466-173">See the code examples in this section for examples.</span></span>

<span data-ttu-id="b9466-174">O `option` tipo é uma união discriminada que tem dois casos `Some` e `None` .</span><span class="sxs-lookup"><span data-stu-id="b9466-174">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="b9466-175">Um case ( `Some` ) tem um valor, mas o outro ( `None` ) é apenas um caso nomeado.</span><span class="sxs-lookup"><span data-stu-id="b9466-175">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="b9466-176">Portanto, `Some` o precisa ter uma variável para o valor associado ao `Some` caso, mas `None` deve aparecer por si só.</span><span class="sxs-lookup"><span data-stu-id="b9466-176">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="b9466-177">No código a seguir, a variável `var1` recebe o valor obtido pela correspondência ao `Some` caso.</span><span class="sxs-lookup"><span data-stu-id="b9466-177">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="b9466-178">No exemplo a seguir, a `PersonName` união discriminada contém uma mistura de cadeias e caracteres que representam possíveis formas de nomes.</span><span class="sxs-lookup"><span data-stu-id="b9466-178">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="b9466-179">Os casos da união discriminada são `FirstOnly` , `LastOnly` e `FirstLast` .</span><span class="sxs-lookup"><span data-stu-id="b9466-179">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="b9466-180">Para uniões discriminadas que têm campos nomeados, use o sinal de igual (=) para extrair o valor de um campo nomeado.</span><span class="sxs-lookup"><span data-stu-id="b9466-180">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="b9466-181">Por exemplo, considere uma união discriminada com uma declaração como a seguinte.</span><span class="sxs-lookup"><span data-stu-id="b9466-181">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="b9466-182">Você pode usar os campos nomeados em uma expressão de correspondência de padrões da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="b9466-182">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="b9466-183">O uso do campo nomeado é opcional, portanto, no exemplo anterior, ambos `Circle(r)` e `Circle(radius = r)` têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="b9466-183">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="b9466-184">Quando você especifica vários campos, use o ponto-e-vírgula (;) como um separador.</span><span class="sxs-lookup"><span data-stu-id="b9466-184">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```fsharp
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="b9466-185">Os padrões ativos permitem definir correspondência de padrões personalizados mais complexos.</span><span class="sxs-lookup"><span data-stu-id="b9466-185">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="b9466-186">Para obter mais informações sobre padrões ativos, consulte [padrões ativos](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="b9466-186">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="b9466-187">O caso em que o identificador é uma exceção é usado na correspondência de padrões no contexto de manipuladores de exceção.</span><span class="sxs-lookup"><span data-stu-id="b9466-187">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="b9466-188">Para obter informações sobre correspondência de padrões no tratamento de exceção, consulte [Exceptions: The `try...with` expression](./exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="b9466-188">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="b9466-189">Padrões de variáveis</span><span class="sxs-lookup"><span data-stu-id="b9466-189">Variable Patterns</span></span>

<span data-ttu-id="b9466-190">O padrão variável atribui o valor que está sendo correspondido a um nome de variável, que está disponível para uso na expressão de execução à direita do `->` símbolo.</span><span class="sxs-lookup"><span data-stu-id="b9466-190">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="b9466-191">Um padrão variável sozinho corresponde A qualquer entrada, mas padrões de variáveis geralmente aparecem dentro de outros padrões, permitindo, portanto, estruturas mais complexas, como tuplas e matrizes a serem decompostas em variáveis.</span><span class="sxs-lookup"><span data-stu-id="b9466-191">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="b9466-192">O exemplo a seguir demonstra um padrão variável dentro de um padrão de tupla.</span><span class="sxs-lookup"><span data-stu-id="b9466-192">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="b9466-193">como padrão</span><span class="sxs-lookup"><span data-stu-id="b9466-193">as Pattern</span></span>

<span data-ttu-id="b9466-194">O `as` padrão é um padrão que tem uma `as` cláusula acrescentada a ele.</span><span class="sxs-lookup"><span data-stu-id="b9466-194">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="b9466-195">A `as` cláusula associa o valor correspondente a um nome que pode ser usado na expressão de execução de uma `match` expressão ou, no caso em que esse padrão é usado em uma `let` associação, o nome é adicionado como uma associação ao escopo local.</span><span class="sxs-lookup"><span data-stu-id="b9466-195">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="b9466-196">O exemplo a seguir usa um `as` padrão.</span><span class="sxs-lookup"><span data-stu-id="b9466-196">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="b9466-197">OU padrão</span><span class="sxs-lookup"><span data-stu-id="b9466-197">OR Pattern</span></span>

<span data-ttu-id="b9466-198">O padrão ou é usado quando os dados de entrada podem corresponder a vários padrões e você deseja executar o mesmo código como resultado.</span><span class="sxs-lookup"><span data-stu-id="b9466-198">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="b9466-199">Os tipos de ambos os lados do padrão ou devem ser compatíveis.</span><span class="sxs-lookup"><span data-stu-id="b9466-199">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="b9466-200">O exemplo a seguir demonstra o padrão ou.</span><span class="sxs-lookup"><span data-stu-id="b9466-200">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="b9466-201">E padrão</span><span class="sxs-lookup"><span data-stu-id="b9466-201">AND Pattern</span></span>

<span data-ttu-id="b9466-202">O padrão AND requer que a entrada corresponda a dois padrões.</span><span class="sxs-lookup"><span data-stu-id="b9466-202">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="b9466-203">Os tipos de ambos os lados do padrão e devem ser compatíveis.</span><span class="sxs-lookup"><span data-stu-id="b9466-203">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="b9466-204">O exemplo a seguir é como `detectZeroTuple` mostrado na seção padrão de tupla mais adiante neste tópico, mas aqui `var1` e `var2` são obtidos como valores usando o padrão e.</span><span class="sxs-lookup"><span data-stu-id="b9466-204">The following example is like `detectZeroTuple` shown in the Tuple Pattern section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="b9466-205">Padrão de contras</span><span class="sxs-lookup"><span data-stu-id="b9466-205">Cons Pattern</span></span>

<span data-ttu-id="b9466-206">O padrão de contras de contras é usado para decompor uma lista no primeiro elemento, no *cabeçalho* e em uma lista que contém os elementos restantes, a *parte final*.</span><span class="sxs-lookup"><span data-stu-id="b9466-206">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="b9466-207">Padrão de lista</span><span class="sxs-lookup"><span data-stu-id="b9466-207">List Pattern</span></span>

<span data-ttu-id="b9466-208">O padrão de lista permite que as listas sejam decompostas em vários elementos.</span><span class="sxs-lookup"><span data-stu-id="b9466-208">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="b9466-209">O próprio padrão de lista pode corresponder apenas a listas de um número específico de elementos.</span><span class="sxs-lookup"><span data-stu-id="b9466-209">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="b9466-210">Padrão de matriz</span><span class="sxs-lookup"><span data-stu-id="b9466-210">Array Pattern</span></span>

<span data-ttu-id="b9466-211">O padrão de matriz é semelhante ao padrão de lista e pode ser usado para decompor matrizes de um comprimento específico.</span><span class="sxs-lookup"><span data-stu-id="b9466-211">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="b9466-212">Padrão entre parênteses</span><span class="sxs-lookup"><span data-stu-id="b9466-212">Parenthesized Pattern</span></span>

<span data-ttu-id="b9466-213">Os parênteses podem ser agrupados de acordo com os padrões para alcançar a associação desejada.</span><span class="sxs-lookup"><span data-stu-id="b9466-213">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="b9466-214">No exemplo a seguir, os parênteses são usados para controlar a associação entre um padrão e um padrão de contras.</span><span class="sxs-lookup"><span data-stu-id="b9466-214">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="b9466-215">Padrão de tupla</span><span class="sxs-lookup"><span data-stu-id="b9466-215">Tuple Pattern</span></span>

<span data-ttu-id="b9466-216">O padrão de tupla corresponde à entrada no formulário de tupla e permite que a tupla seja decomposta em seus elementos constituintes usando variáveis de correspondência de padrões para cada posição na tupla.</span><span class="sxs-lookup"><span data-stu-id="b9466-216">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="b9466-217">O exemplo a seguir demonstra o padrão de tupla e também usa padrões literais, padrões variáveis e o padrão curinga.</span><span class="sxs-lookup"><span data-stu-id="b9466-217">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="b9466-218">Padrão de registro</span><span class="sxs-lookup"><span data-stu-id="b9466-218">Record Pattern</span></span>

<span data-ttu-id="b9466-219">O padrão de registro é usado para decompor registros para extrair os valores dos campos.</span><span class="sxs-lookup"><span data-stu-id="b9466-219">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="b9466-220">O padrão não precisa fazer referência a todos os campos do registro; os campos omitidos simplesmente não participam da correspondência e não são extraídos.</span><span class="sxs-lookup"><span data-stu-id="b9466-220">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="b9466-221">Padrão de curinga</span><span class="sxs-lookup"><span data-stu-id="b9466-221">Wildcard Pattern</span></span>

<span data-ttu-id="b9466-222">O padrão de caractere curinga é representado pelo caractere de sublinhado ( `_` ) e corresponde a qualquer entrada, assim como o padrão de variável, exceto que a entrada é descartada em vez de atribuída a uma variável.</span><span class="sxs-lookup"><span data-stu-id="b9466-222">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="b9466-223">O padrão de caractere curinga geralmente é usado em outros padrões como um espaço reservado para valores que não são necessários na expressão à direita do `->` símbolo.</span><span class="sxs-lookup"><span data-stu-id="b9466-223">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="b9466-224">O padrão curinga também é usado frequentemente no final de uma lista de padrões para corresponder a qualquer entrada sem correspondência.</span><span class="sxs-lookup"><span data-stu-id="b9466-224">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="b9466-225">O padrão de curinga é demonstrado em muitos exemplos de código neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b9466-225">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="b9466-226">Consulte o código anterior para obter um exemplo.</span><span class="sxs-lookup"><span data-stu-id="b9466-226">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="b9466-227">Padrões que têm anotações de tipo</span><span class="sxs-lookup"><span data-stu-id="b9466-227">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="b9466-228">Os padrões podem ter anotações de tipo.</span><span class="sxs-lookup"><span data-stu-id="b9466-228">Patterns can have type annotations.</span></span> <span data-ttu-id="b9466-229">Eles se comportam como outras anotações de tipo e inferência de guia como outras anotações de tipo.</span><span class="sxs-lookup"><span data-stu-id="b9466-229">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="b9466-230">Os parênteses são necessários em relação a anotações de tipo em padrões.</span><span class="sxs-lookup"><span data-stu-id="b9466-230">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="b9466-231">O código a seguir mostra um padrão que tem uma anotação de tipo.</span><span class="sxs-lookup"><span data-stu-id="b9466-231">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="b9466-232">Padrão de teste de tipo</span><span class="sxs-lookup"><span data-stu-id="b9466-232">Type Test Pattern</span></span>

<span data-ttu-id="b9466-233">O padrão de teste de tipo é usado para corresponder à entrada em relação a um tipo.</span><span class="sxs-lookup"><span data-stu-id="b9466-233">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="b9466-234">Se o tipo de entrada for uma correspondência (ou um tipo derivado) do tipo especificado no padrão, a correspondência será realizada com sucesso.</span><span class="sxs-lookup"><span data-stu-id="b9466-234">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="b9466-235">O exemplo a seguir demonstra o tipo de padrão de teste.</span><span class="sxs-lookup"><span data-stu-id="b9466-235">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

<span data-ttu-id="b9466-236">Se você estiver verificando apenas se um identificador é de um tipo derivado específico, não precisará da `as identifier` parte do padrão, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="b9466-236">If you're only checking if an identifier is of a particular derived type, you don't need the `as identifier` part of the pattern, as shown in the following example:</span></span>

```fsharp
type A() = class end
type B() = inherit A()
type C() = inherit A()

let m (a: A) =
    match a with
    | :? B -> printfn "It's a B"
    | :? C -> printfn "It's a C"
    | _ -> ()
```

## <a name="null-pattern"></a><span data-ttu-id="b9466-237">Padrão nulo</span><span class="sxs-lookup"><span data-stu-id="b9466-237">Null Pattern</span></span>

<span data-ttu-id="b9466-238">O padrão nulo corresponde ao valor nulo que pode aparecer quando você está trabalhando com tipos que permitem um valor nulo.</span><span class="sxs-lookup"><span data-stu-id="b9466-238">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="b9466-239">Padrões nulos são usados frequentemente quando interoperam com código .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b9466-239">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="b9466-240">Por exemplo, o valor de retorno de uma API do .NET pode ser a entrada para uma `match` expressão.</span><span class="sxs-lookup"><span data-stu-id="b9466-240">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="b9466-241">Você pode controlar o fluxo do programa com base em se o valor de retorno é nulo e também em outras características do valor retornado.</span><span class="sxs-lookup"><span data-stu-id="b9466-241">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="b9466-242">Você pode usar o padrão nulo para impedir que valores nulos se propaguem para o restante do seu programa.</span><span class="sxs-lookup"><span data-stu-id="b9466-242">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="b9466-243">O exemplo a seguir usa o padrão nulo e o padrão de variável.</span><span class="sxs-lookup"><span data-stu-id="b9466-243">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="nameof-pattern"></a><span data-ttu-id="b9466-244">Padrão nameof</span><span class="sxs-lookup"><span data-stu-id="b9466-244">Nameof pattern</span></span>

<span data-ttu-id="b9466-245">O `nameof` padrão corresponde a uma cadeia de caracteres quando seu valor é igual à expressão que segue a `nameof` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="b9466-245">The `nameof` pattern matches against a string when its value is equal to the expression that follows the `nameof` keyword.</span></span> <span data-ttu-id="b9466-246">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b9466-246">for example:</span></span>

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```

<span data-ttu-id="b9466-247">Consulte o [`nameof`](nameof.md) operador para obter informações sobre o que você pode obter um nome.</span><span class="sxs-lookup"><span data-stu-id="b9466-247">See the [`nameof`](nameof.md) operator for information on what you can take a name of.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9466-248">Veja também</span><span class="sxs-lookup"><span data-stu-id="b9466-248">See also</span></span>

- [<span data-ttu-id="b9466-249">Expressões de correspondência</span><span class="sxs-lookup"><span data-stu-id="b9466-249">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="b9466-250">Padrões ativos</span><span class="sxs-lookup"><span data-stu-id="b9466-250">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="b9466-251">Referência de linguagem F #</span><span class="sxs-lookup"><span data-stu-id="b9466-251">F# Language Reference</span></span>](index.md)
