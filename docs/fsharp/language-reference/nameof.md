---
title: Nameof
description: Saiba mais sobre o operador nameof, um recurso de metaprogramação que permite que você produza o nome de qualquer símbolo em seu código-fonte.
ms.date: 11/12/2020
ms.openlocfilehash: 9947d7172d1b73db5c181297ec8b1131382e1f5e
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688598"
---
# <a name="nameof"></a><span data-ttu-id="2c325-103">Nameof</span><span class="sxs-lookup"><span data-stu-id="2c325-103">Nameof</span></span>

<span data-ttu-id="2c325-104">A `nameof` expressão produz uma constante de cadeia de caracteres que corresponde ao nome na origem de quase qualquer construção F # na origem.</span><span class="sxs-lookup"><span data-stu-id="2c325-104">The `nameof` expression produces a string constant that matches the name in source for nearly any F# construct in source.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c325-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2c325-105">Syntax</span></span>

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a><span data-ttu-id="2c325-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="2c325-106">Remarks</span></span>

<span data-ttu-id="2c325-107">`nameof` funciona resolvendo o símbolo passado para ele e produz o nome desse símbolo como ele é declarado em seu código-fonte.</span><span class="sxs-lookup"><span data-stu-id="2c325-107">`nameof` works by resolving the symbol passed to it and produces the name of that symbol as it is declared in your source code.</span></span> <span data-ttu-id="2c325-108">Isso é útil em vários cenários, como registro em log e protege o registro em log contra alterações no código-fonte.</span><span class="sxs-lookup"><span data-stu-id="2c325-108">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) ($"Value passed in was %d{month}.")

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

<span data-ttu-id="2c325-109">A última linha gerará uma exceção e `"month"` será mostrada na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="2c325-109">The last line will throw an exception and `"month"` will be shown in the error message.</span></span>

<span data-ttu-id="2c325-110">Você pode usar um nome de quase todas as construções em F #:</span><span class="sxs-lookup"><span data-stu-id="2c325-110">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

<span data-ttu-id="2c325-111">`nameof` Não é uma função de primeira classe e não pode ser usada como tal.</span><span class="sxs-lookup"><span data-stu-id="2c325-111">`nameof` is not a first-class function and cannot be used as such.</span></span> <span data-ttu-id="2c325-112">Isso significa que ele não pode ser parcialmente aplicado e os valores não podem ser redirecionados para ele por meio de operadores de pipeline de F #.</span><span class="sxs-lookup"><span data-stu-id="2c325-112">That means it cannot be partially applied and values cannot be piped into it via F# pipeline operators.</span></span>

## <a name="nameof-on-operators"></a><span data-ttu-id="2c325-113">Nameof em operadores</span><span class="sxs-lookup"><span data-stu-id="2c325-113">Nameof on operators</span></span>

<span data-ttu-id="2c325-114">Os operadores em F # podem ser usados de duas maneiras, como um texto de operador ou um símbolo que representa o formulário compilado.</span><span class="sxs-lookup"><span data-stu-id="2c325-114">Operators in F# can be used in two ways, as an operator text itself, or a symbol representing the compiled form.</span></span> <span data-ttu-id="2c325-115">`nameof` em um operador produzirá o nome do operador como ele é declarado na origem.</span><span class="sxs-lookup"><span data-stu-id="2c325-115">`nameof` on an operator will produce the name of the operator as it is declared in source.</span></span> <span data-ttu-id="2c325-116">Para obter o nome compilado, use o nome compilado em Source:</span><span class="sxs-lookup"><span data-stu-id="2c325-116">To get the compiled name, use the compiled name in source:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a><span data-ttu-id="2c325-117">Nameof em genéricos</span><span class="sxs-lookup"><span data-stu-id="2c325-117">Nameof on generics</span></span>

<span data-ttu-id="2c325-118">Você também pode usar um nome de parâmetro de tipo genérico, mas a sintaxe é diferente:</span><span class="sxs-lookup"><span data-stu-id="2c325-118">You can also take a name of a generic type parameter, but the syntax is different:</span></span>

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

<span data-ttu-id="2c325-119">`nameof<'TGeneric>` obterá o nome do símbolo conforme definido em Source, não o nome do tipo substituído em um site de chamada.</span><span class="sxs-lookup"><span data-stu-id="2c325-119">`nameof<'TGeneric>` will take the name of the symbol as defined in source, not the name of the type substituted at a call site.</span></span>

<span data-ttu-id="2c325-120">O motivo pelo qual a sintaxe é diferente é alinhar com outros operadores intrínsecos em F # como `typeof<>` e `typedefof<>` .</span><span class="sxs-lookup"><span data-stu-id="2c325-120">The reason why the syntax is different is to align with other F# intrinsic operators like `typeof<>` and `typedefof<>`.</span></span> <span data-ttu-id="2c325-121">Isso torna o F # consistente com relação aos operadores que atuam em tipos genéricos e qualquer outra coisa na origem.</span><span class="sxs-lookup"><span data-stu-id="2c325-121">This makes F# consistent with respect to operators that act on generic types and anything else in source.</span></span>

## <a name="nameof-in-pattern-matching"></a><span data-ttu-id="2c325-122">Nameof na correspondência de padrões</span><span class="sxs-lookup"><span data-stu-id="2c325-122">Nameof in pattern matching</span></span>

<span data-ttu-id="2c325-123">O [ `nameof` padrão](pattern-matching.md#nameof-pattern) permite que você use `nameof` em uma expressão de correspondência de padrões como esta:</span><span class="sxs-lookup"><span data-stu-id="2c325-123">The [`nameof` pattern](pattern-matching.md#nameof-pattern) lets you use `nameof` in a pattern match expression like so:</span></span>

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
