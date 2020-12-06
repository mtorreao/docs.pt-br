---
title: Fatias
description: 'Saiba como usar fatias para tipos de dados F # existentes e como definir suas próprias fatias para outros tipos de dados.'
ms.date: 11/20/2020
ms.openlocfilehash: b776058df5a174dfe48dbf513bf17281036dd83e
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740374"
---
# <a name="slices"></a><span data-ttu-id="f89a3-103">Fatias</span><span class="sxs-lookup"><span data-stu-id="f89a3-103">Slices</span></span>

<span data-ttu-id="f89a3-104">Este artigo explica como tirar fatias de tipos existentes de F # e como definir suas próprias fatias.</span><span class="sxs-lookup"><span data-stu-id="f89a3-104">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="f89a3-105">Em F #, uma fatia é um subconjunto de qualquer tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="f89a3-105">In F#, a slice is a subset of any data type.</span></span>  <span data-ttu-id="f89a3-106">As fatias são semelhantes aos [indexadores](./members/indexed-properties.md), mas em vez de produzir um único valor da estrutura de dados subjacente, elas produzem várias delas.</span><span class="sxs-lookup"><span data-stu-id="f89a3-106">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span> <span data-ttu-id="f89a3-107">As fatias usam a `..` sintaxe do operador para selecionar o intervalo de índices especificados em um tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="f89a3-107">Slices use the `..` operator syntax to select the range of specified indices in a data type.</span></span> <span data-ttu-id="f89a3-108">Para obter mais informações, consulte o [artigo referência de expressões de looping](./loops-for-in-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f89a3-108">For more information, see the [looping expression reference article](./loops-for-in-expression.md).</span></span>

<span data-ttu-id="f89a3-109">O F # atualmente tem suporte intrínseco para cadeias de caracteres de divisão, listas, matrizes e matrizes multidimensionais (2D, 3D, 4D).</span><span class="sxs-lookup"><span data-stu-id="f89a3-109">F# currently has intrinsic support for slicing strings, lists, arrays, and multidimensional (2D, 3D, 4D) arrays.</span></span> <span data-ttu-id="f89a3-110">A divisão é mais comumente usada com matrizes e listas de F #.</span><span class="sxs-lookup"><span data-stu-id="f89a3-110">Slicing is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="f89a3-111">Você pode adicionar fatias a seus tipos de dados personalizados usando o `GetSlice` método em sua definição de tipo ou em uma extensão de [tipo](type-extensions.md)no escopo.</span><span class="sxs-lookup"><span data-stu-id="f89a3-111">You can add slicing to your custom data types by using the `GetSlice` method in your type definition or in an in-scope [type extension](type-extensions.md).</span></span>

## <a name="slicing-f-lists-and-arrays"></a><span data-ttu-id="f89a3-112">Divisão de listas e matrizes de F #</span><span class="sxs-lookup"><span data-stu-id="f89a3-112">Slicing F# lists and arrays</span></span>

<span data-ttu-id="f89a3-113">Os tipos de dados mais comuns que são segmentados são listas e matrizes de F #.</span><span class="sxs-lookup"><span data-stu-id="f89a3-113">The most common data types that are sliced are F# lists and arrays.</span></span>  <span data-ttu-id="f89a3-114">O exemplo a seguir demonstra como segmentar listas:</span><span class="sxs-lookup"><span data-stu-id="f89a3-114">The following example demonstrates how to slice lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn $"Small slice: {smallSlice}"

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn $"Unbounded beginning slice: {unboundedBeginning}"

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn $"Unbounded end slice: {unboundedEnd}"
```

<span data-ttu-id="f89a3-115">As matrizes de divisão são apenas como listas de fatias:</span><span class="sxs-lookup"><span data-stu-id="f89a3-115">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn $"Small slice: {smallSlice}"

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn $"Unbounded beginning slice: {unboundedBeginning}"

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn $"Unbounded end slice: {unboundedEnd}"
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="f89a3-116">Fatiando matrizes multidimensionais</span><span class="sxs-lookup"><span data-stu-id="f89a3-116">Slicing multidimensional arrays</span></span>

<span data-ttu-id="f89a3-117">O f # dá suporte a matrizes multidimensionais na biblioteca principal do F #.</span><span class="sxs-lookup"><span data-stu-id="f89a3-117">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="f89a3-118">Assim como acontece com matrizes unidimensionais, as fatias de matrizes multidimensionais também podem ser úteis.</span><span class="sxs-lookup"><span data-stu-id="f89a3-118">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="f89a3-119">No entanto, a introdução de dimensões adicionais exige uma sintaxe ligeiramente diferente para que você possa colocar fatias de linhas e colunas específicas.</span><span class="sxs-lookup"><span data-stu-id="f89a3-119">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="f89a3-120">Os exemplos a seguir demonstram como dividir uma matriz 2D:</span><span class="sxs-lookup"><span data-stu-id="f89a3-120">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn $"Full matrix:\n {A}"

// Take the first row
let row0 = A.[0,*]
printfn $"{row0}"

// Take the first column
let col0 = A.[*,0]
printfn $"{col0}"

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn $"{subA}"

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn $"{subA}"

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn $"{twoByTwo}"
```

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="f89a3-121">Definindo fatias para outras estruturas de dados</span><span class="sxs-lookup"><span data-stu-id="f89a3-121">Defining slices for other data structures</span></span>

<span data-ttu-id="f89a3-122">A biblioteca de núcleos F # define fatias para um conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="f89a3-122">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="f89a3-123">Se você quiser definir fatias para mais tipos de dados, poderá fazer isso na própria definição de tipo ou em uma extensão de tipo.</span><span class="sxs-lookup"><span data-stu-id="f89a3-123">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="f89a3-124">Por exemplo, veja como você pode definir fatias para a <xref:System.ArraySegment%601> classe para permitir uma manipulação de dados conveniente:</span><span class="sxs-lookup"><span data-stu-id="f89a3-124">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

<span data-ttu-id="f89a3-125">Outro exemplo que usa <xref:System.Span%601> os <xref:System.ReadOnlySpan%601> tipos e:</span><span class="sxs-lookup"><span data-stu-id="f89a3-125">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

```fsharp
open System

type ReadOnlySpan<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn $"{arr}"

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..3] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="f89a3-126">As fatias F # internas são inclusivas</span><span class="sxs-lookup"><span data-stu-id="f89a3-126">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="f89a3-127">Todas as fatias intrínsecas em F # são inclusivas; ou seja, o limite superior é incluído na fatia.</span><span class="sxs-lookup"><span data-stu-id="f89a3-127">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="f89a3-128">Para uma determinada fatia com índice inicial `x` e índice final `y` , a fatia resultante incluirá o valor *YTH* .</span><span class="sxs-lookup"><span data-stu-id="f89a3-128">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn $"{xs.[2..5]}" // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a><span data-ttu-id="f89a3-129">Fatias internas F # vazias</span><span class="sxs-lookup"><span data-stu-id="f89a3-129">Built-in F# empty slices</span></span>

<span data-ttu-id="f89a3-130">As listas de F #, matrizes, sequências, cadeias de caracteres, matrizes multidimensionais (2D, 3D, 4D) produzirão uma fatia vazia se a sintaxe puder produzir uma fatia que não existe.</span><span class="sxs-lookup"><span data-stu-id="f89a3-130">F# lists, arrays, sequences, strings, multidimensional (2D, 3D, 4D) arrays will all produce an empty slice if the syntax could produce a slice that doesn't exist.</span></span>

<span data-ttu-id="f89a3-131">Considere o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="f89a3-131">Consider the following example:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

> [!IMPORTANT]
> <span data-ttu-id="f89a3-132">Os desenvolvedores de C# podem esperar que eles lancem uma exceção em vez de produzir uma fatia vazia.</span><span class="sxs-lookup"><span data-stu-id="f89a3-132">C# developers may expect these to throw an exception rather than produce an empty slice.</span></span> <span data-ttu-id="f89a3-133">Essa é uma decisão de design enraizada no fato de que coleções vazias compõem em F #.</span><span class="sxs-lookup"><span data-stu-id="f89a3-133">This is a design decision rooted in the fact that empty collections compose in F#.</span></span> <span data-ttu-id="f89a3-134">Uma lista de F # vazia pode ser composta com outra lista de F #, uma cadeia de caracteres vazia pode ser adicionada a uma cadeia de caracteres existente e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f89a3-134">An empty F# list can be composed with another F# list, an empty string can be added to an existing string, and so on.</span></span> <span data-ttu-id="f89a3-135">Pode ser comum pegar fatias com base em valores passados como parâmetros, e ser tolerante a fora dos limites > por meio da produção de uma coleção vazia cabe à natureza composicional do código F #.</span><span class="sxs-lookup"><span data-stu-id="f89a3-135">It can be common to take slices based on values passed in as parameters, and being tolerant of out-of-bounds > by producing an empty collection fits with the compositional nature of F# code.</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a><span data-ttu-id="f89a3-136">Fatias de índice fixo para matrizes 3D e 4D</span><span class="sxs-lookup"><span data-stu-id="f89a3-136">Fixed-index slices for 3D and 4D arrays</span></span>

<span data-ttu-id="f89a3-137">Para matrizes F # 3D e 4D, você pode "corrigir" um índice específico e fatiar outras dimensões com esse índice fixo.</span><span class="sxs-lookup"><span data-stu-id="f89a3-137">For F# 3D and 4D arrays, you can "fix" a particular index and slice other dimensions with that index fixed.</span></span>

<span data-ttu-id="f89a3-138">Para ilustrar isso, considere a seguinte matriz 3D:</span><span class="sxs-lookup"><span data-stu-id="f89a3-138">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="f89a3-139">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="f89a3-139">*z = 0*</span></span>

| <span data-ttu-id="f89a3-140">x\y</span><span class="sxs-lookup"><span data-stu-id="f89a3-140">x\y</span></span>   | <span data-ttu-id="f89a3-141">0</span><span class="sxs-lookup"><span data-stu-id="f89a3-141">0</span></span> | <span data-ttu-id="f89a3-142">1</span><span class="sxs-lookup"><span data-stu-id="f89a3-142">1</span></span> |
|-------|---|---|
| <span data-ttu-id="f89a3-143">**0**</span><span class="sxs-lookup"><span data-stu-id="f89a3-143">**0**</span></span> | <span data-ttu-id="f89a3-144">0</span><span class="sxs-lookup"><span data-stu-id="f89a3-144">0</span></span> | <span data-ttu-id="f89a3-145">1</span><span class="sxs-lookup"><span data-stu-id="f89a3-145">1</span></span> |
| <span data-ttu-id="f89a3-146">**1**</span><span class="sxs-lookup"><span data-stu-id="f89a3-146">**1**</span></span> | <span data-ttu-id="f89a3-147">2</span><span class="sxs-lookup"><span data-stu-id="f89a3-147">2</span></span> | <span data-ttu-id="f89a3-148">3</span><span class="sxs-lookup"><span data-stu-id="f89a3-148">3</span></span> |

<span data-ttu-id="f89a3-149">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="f89a3-149">*z = 1*</span></span>

| <span data-ttu-id="f89a3-150">x\y</span><span class="sxs-lookup"><span data-stu-id="f89a3-150">x\y</span></span>   | <span data-ttu-id="f89a3-151">0</span><span class="sxs-lookup"><span data-stu-id="f89a3-151">0</span></span> | <span data-ttu-id="f89a3-152">1</span><span class="sxs-lookup"><span data-stu-id="f89a3-152">1</span></span> |
|-------|---|---|
| <span data-ttu-id="f89a3-153">**0**</span><span class="sxs-lookup"><span data-stu-id="f89a3-153">**0**</span></span> | <span data-ttu-id="f89a3-154">4</span><span class="sxs-lookup"><span data-stu-id="f89a3-154">4</span></span> | <span data-ttu-id="f89a3-155">5</span><span class="sxs-lookup"><span data-stu-id="f89a3-155">5</span></span> |
| <span data-ttu-id="f89a3-156">**1**</span><span class="sxs-lookup"><span data-stu-id="f89a3-156">**1**</span></span> | <span data-ttu-id="f89a3-157">6</span><span class="sxs-lookup"><span data-stu-id="f89a3-157">6</span></span> | <span data-ttu-id="f89a3-158">7</span><span class="sxs-lookup"><span data-stu-id="f89a3-158">7</span></span> |

<span data-ttu-id="f89a3-159">Se você quiser extrair a fatia `[| 4; 5 |]` da matriz, use uma fatia de índice fixo.</span><span class="sxs-lookup"><span data-stu-id="f89a3-159">If you want to extract the slice `[| 4; 5 |]` from the array, use a fixed-index slice.</span></span>

```fsharp
let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

<span data-ttu-id="f89a3-160">A última linha corrige os `y` `z` índices e da matriz 3D e leva o restante dos `x` valores que correspondem à matriz.</span><span class="sxs-lookup"><span data-stu-id="f89a3-160">The last line fixes the `y` and `z` indices of the 3D array and takes the rest of the `x` values that correspond to the matrix.</span></span>

## <a name="see-also"></a><span data-ttu-id="f89a3-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="f89a3-161">See also</span></span>

- [<span data-ttu-id="f89a3-162">Propriedades indexadas</span><span class="sxs-lookup"><span data-stu-id="f89a3-162">Indexed properties</span></span>](./members/indexed-properties.md)
