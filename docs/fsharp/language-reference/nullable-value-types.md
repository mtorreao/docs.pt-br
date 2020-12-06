---
title: Tipos de valor anuláveis
description: 'Saiba como usar tipos de valor anulável, uma maneira de representar um tipo de valor que também pode ser NULL, em F #.'
ms.date: 11/19/2020
ms.openlocfilehash: da0cd85bd651db81ba98c02a9db31d92dc52a8c6
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740399"
---
# <a name="nullable-value-types"></a><span data-ttu-id="4443c-103">Tipos de valor anuláveis</span><span class="sxs-lookup"><span data-stu-id="4443c-103">Nullable value types</span></span>

<span data-ttu-id="4443c-104">Um _tipo de valor anulável_ `Nullable<'T>` representa qualquer tipo de [struct](structures.md) que também pode ser `null` .</span><span class="sxs-lookup"><span data-stu-id="4443c-104">A _nullable value type_ `Nullable<'T>` represents any [struct](structures.md) type that could also be `null`.</span></span> <span data-ttu-id="4443c-105">Isso é útil ao interagir com bibliotecas e componentes que podem escolher representar esses tipos de tipos, como inteiros, com um `null` valor por motivos de eficiência.</span><span class="sxs-lookup"><span data-stu-id="4443c-105">This is helpful when interacting with libraries and components that may choose to represent these kinds of types, like integers, with a `null` value for efficiency reasons.</span></span> <span data-ttu-id="4443c-106">O tipo subjacente que faz backup desse constructo é <xref:System.Nullable%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4443c-106">The underlying type that backs this construct is <xref:System.Nullable%601?displayProperty=nameWithType>.</span></span>

## <a name="syntax"></a><span data-ttu-id="4443c-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4443c-107">Syntax</span></span>

```fsharp
Nullable<'T>
Nullable value
```

## <a name="declare-and-assign-with-values"></a><span data-ttu-id="4443c-108">Declarar e atribuir com valores</span><span class="sxs-lookup"><span data-stu-id="4443c-108">Declare and assign with values</span></span>

<span data-ttu-id="4443c-109">Declarar um tipo de valor anulável é exatamente como declarar qualquer tipo de wrapper em F #:</span><span class="sxs-lookup"><span data-stu-id="4443c-109">Declaring a nullable value type is just like declaring any wrapper-like type in F#:</span></span>

```fsharp
open System

let x = 12
let nullableX = Nullable<int> x
```

<span data-ttu-id="4443c-110">Você também pode Elide o parâmetro de tipo genérico e permitir que a inferência de tipos o resolva:</span><span class="sxs-lookup"><span data-stu-id="4443c-110">You can also elide the generic type parameter and allow type inference to resolve it:</span></span>

```fsharp
open System

let x = 12
let nullableX = Nullable x
```

<span data-ttu-id="4443c-111">Para atribuir a um tipo de valor anulável, você também precisará ser explícito.</span><span class="sxs-lookup"><span data-stu-id="4443c-111">To assign to a nullable value type, you'll need to also be explicit.</span></span> <span data-ttu-id="4443c-112">Não há conversão implícita para tipos de valores anuláveis definidos em F #:</span><span class="sxs-lookup"><span data-stu-id="4443c-112">There is no implicit conversion for F#-defined nullable value types:</span></span>

```fsharp
open System

let mutable x = Nullable 12
x <- Nullable 13
```

## <a name="assign-null"></a><span data-ttu-id="4443c-113">Atribuir nulo</span><span class="sxs-lookup"><span data-stu-id="4443c-113">Assign null</span></span>

<span data-ttu-id="4443c-114">Não é possível atribuir diretamente `null` a um tipo de valor anulável.</span><span class="sxs-lookup"><span data-stu-id="4443c-114">You cannot directly assign `null` to a nullable value type.</span></span> <span data-ttu-id="4443c-115">Use `Nullable()` em vez disso:</span><span class="sxs-lookup"><span data-stu-id="4443c-115">Use `Nullable()` instead:</span></span>

```fsharp
let mutable a = Nullable 42
a <- Nullable()
```

<span data-ttu-id="4443c-116">Isso ocorre porque `Nullable<'T>` o não tem `null` um valor adequado.</span><span class="sxs-lookup"><span data-stu-id="4443c-116">This is because `Nullable<'T>` does not have `null` as a proper value.</span></span>

## <a name="pass-and-assign-to-members"></a><span data-ttu-id="4443c-117">Passar e atribuir a membros</span><span class="sxs-lookup"><span data-stu-id="4443c-117">Pass and assign to members</span></span>

<span data-ttu-id="4443c-118">Uma diferença importante entre trabalhar com membros e valores F # é que os tipos de valores anuláveis podem ser inferidos implicitamente quando você estiver trabalhando com membros.</span><span class="sxs-lookup"><span data-stu-id="4443c-118">A key difference between working with members and F# values is that nullable value types can be implicitly inferred when you're working with members.</span></span> <span data-ttu-id="4443c-119">Considere o método folling que usa um tipo de valor anulável como entrada:</span><span class="sxs-lookup"><span data-stu-id="4443c-119">Consider the folling method that takes a nullable value type as input:</span></span>

```fsharp
type C() =
    member _.M(x: Nullable<int>) = x.HasValue
    member val NVT = Nullable 12 with get, set

let c = C()
c.M(12)
c.NVT <- 12
```

<span data-ttu-id="4443c-120">No exemplo anterior, você pode passar `12` para o método `M` .</span><span class="sxs-lookup"><span data-stu-id="4443c-120">In the previous example, you can pass `12` to the method `M`.</span></span> <span data-ttu-id="4443c-121">Você também pode atribuir `12` à propriedade auto `NVT` .</span><span class="sxs-lookup"><span data-stu-id="4443c-121">You can also assign `12` to the auto property `NVT`.</span></span> <span data-ttu-id="4443c-122">O compilador F # converterá implicitamente uma chamada ou atribuição como esta quando o tipo de destino corresponder à entrada, se a entrada puder ser construída como um tipo de valor nullabel.</span><span class="sxs-lookup"><span data-stu-id="4443c-122">The F# compiler will implicitly convert a call or assignment like this when the target type matches the input, if the input can be constructed as a nullabel value type.</span></span>

## <a name="examine-a-nullable-value-type-instance"></a><span data-ttu-id="4443c-123">Examinar uma instância de tipo de valor anulável</span><span class="sxs-lookup"><span data-stu-id="4443c-123">Examine a nullable value type instance</span></span>

<span data-ttu-id="4443c-124">Ao contrário das [Opções](options.md), que são uma construção generalizada para representar um valor possível, os tipos de valores anuláveis não são usados com correspondência de padrões.</span><span class="sxs-lookup"><span data-stu-id="4443c-124">Unlike [Options](options.md), which are a generalized construct for representing a possible value, nullable value types are not used with pattern matching.</span></span> <span data-ttu-id="4443c-125">Em vez disso, você precisa usar uma [`if`](conditional-expressions-if-then-else.md) expressão e verificar a `HasValue` propriedade.</span><span class="sxs-lookup"><span data-stu-id="4443c-125">Instead, you need to use an [`if`](conditional-expressions-if-then-else.md) expression and check the `HasValue` property.</span></span>

<span data-ttu-id="4443c-126">Para obter o valor subjacente, use a `Value` propriedade após uma `HasValue` verificação, desta forma:</span><span class="sxs-lookup"><span data-stu-id="4443c-126">To get the underlying value, use the `Value` property after a `HasValue` check, like so:</span></span>

```fsharp
open System

let a = Nullable 42

if a.HasValue then
    printfn $"{a} is {a.Value}"
else
    printfn $"{a} has no value."
```

## <a name="nullable-operators"></a><span data-ttu-id="4443c-127">Operadores anuláveis</span><span class="sxs-lookup"><span data-stu-id="4443c-127">Nullable operators</span></span>

<span data-ttu-id="4443c-128">As operações em tipos de valores anuláveis, como aritmética ou comparação, podem exigir o uso de [operadores anuláveis](symbol-and-operator-reference/nullable-operators.md).</span><span class="sxs-lookup"><span data-stu-id="4443c-128">Operations on nullable value types, such as arithmetic or comparison, can require the use of [nullable operators](symbol-and-operator-reference/nullable-operators.md).</span></span>

<span data-ttu-id="4443c-129">Você pode converter de um tipo de valor anulável para outro usando operadores de conversão do `FSharp.Linq` namespace:</span><span class="sxs-lookup"><span data-stu-id="4443c-129">You can convert from one nullable value type to another using conversion operators from the `FSharp.Linq` namespace:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt
```

<span data-ttu-id="4443c-130">Você também pode usar um operador não anulável apropriado para converter em um tipo primitivo, arriscando uma exceção se não tiver valor:</span><span class="sxs-lookup"><span data-stu-id="4443c-130">You can also use an appropriate non-nullable operator to convert to a primitive type, risking an exception if it has no value:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

printfn $"value is %f{float nullableFloat}"
```

<span data-ttu-id="4443c-131">Você também pode usar operadores anuláveis como um pequeno para verificar `HasValue` e `Value` :</span><span class="sxs-lookup"><span data-stu-id="4443c-131">You can also use nullable operators as a short-hand for checking `HasValue` and `Value`:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

let isBigger = nullableFloat ?> 1.0
let isBiggerLongForm = nullableFloat.HasValue && nullableFloat.Value > 1.0
```

<span data-ttu-id="4443c-132">A `?>` comparação verifica se o lado esquerdo é anulável e só tem sucesso se tiver um valor.</span><span class="sxs-lookup"><span data-stu-id="4443c-132">The `?>` comparison checks if the left-hand side is nullable and only succeeds if it has a value.</span></span> <span data-ttu-id="4443c-133">É equivalente à linha que a segue.</span><span class="sxs-lookup"><span data-stu-id="4443c-133">It is equivalent to the line that follows it.</span></span>

## <a name="see-also"></a><span data-ttu-id="4443c-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="4443c-134">See also</span></span>

- [<span data-ttu-id="4443c-135">Estruturas</span><span class="sxs-lookup"><span data-stu-id="4443c-135">Structures</span></span>](structures.md)
- [<span data-ttu-id="4443c-136">Opções de F #</span><span class="sxs-lookup"><span data-stu-id="4443c-136">F# Options</span></span>](options.md)
