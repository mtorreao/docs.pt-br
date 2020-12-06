---
title: Resultados
description: "Saiba como usar o tipo ' Result ' de F # para ajudá-lo a escrever código tolerante a erros."
ms.date: 08/13/2020
ms.openlocfilehash: 53b1db0c9224ae032d58c06cd3c58e3dbed03f7b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740218"
---
# <a name="results"></a><span data-ttu-id="f4087-103">Resultados</span><span class="sxs-lookup"><span data-stu-id="f4087-103">Results</span></span>

<span data-ttu-id="f4087-104">O `Result<'T,'TFailure>` tipo permite que você grave código tolerante a erros que pode ser composto.</span><span class="sxs-lookup"><span data-stu-id="f4087-104">The `Result<'T,'TFailure>` type lets you write error-tolerant code that can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4087-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f4087-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="f4087-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="f4087-106">Remarks</span></span>

<span data-ttu-id="f4087-107">Consulte o [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) módulo para os combinadores internos para o `Result` .</span><span class="sxs-lookup"><span data-stu-id="f4087-107">See the [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) module for the built-in combinators for the `Result`.</span></span> <span data-ttu-id="f4087-108">Escreva.</span><span class="sxs-lookup"><span data-stu-id="f4087-108">type.</span></span>

<span data-ttu-id="f4087-109">Observe que o tipo de resultado é uma [união discriminada de struct](discriminated-unions.md#struct-discriminated-unions).</span><span class="sxs-lookup"><span data-stu-id="f4087-109">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions).</span></span> <span data-ttu-id="f4087-110">A semântica de igualdade estrutural se aplica aqui.</span><span class="sxs-lookup"><span data-stu-id="f4087-110">Structural equality semantics apply here.</span></span>

<span data-ttu-id="f4087-111">O `Result` tipo é normalmente usado no tratamento de erros do monadic, que geralmente é conhecido como [programação orientada por ferrovia](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) na Comunidade do F #.</span><span class="sxs-lookup"><span data-stu-id="f4087-111">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="f4087-112">O exemplo trivial a seguir demonstra essa abordagem.</span><span class="sxs-lookup"><span data-stu-id="f4087-112">The following trivial example demonstrates this approach.</span></span>

```fsharp
// Define a simple type which has fields that can be validated
type Request =
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() =
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn $"My request was valid! Name: {req.Name} Email {req.Email}"  
    | Error e -> printfn $"Error: {e}"
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn $"My request was valid! Name: {req.Name} Email {req.Email}"  
    | Error e -> printfn $"Error: {e}"
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="f4087-113">Como você pode ver, é muito fácil encadear várias funções de validação se você forçá-las a retornar um `Result` .</span><span class="sxs-lookup"><span data-stu-id="f4087-113">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="f4087-114">Isso permite que você divida a funcionalidade como esta em pequenas partes, que são tão combináveis quanto você precisa delas.</span><span class="sxs-lookup"><span data-stu-id="f4087-114">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="f4087-115">Isso também tem o valor agregado de *impor* o uso da [correspondência de padrões](pattern-matching.md) no final de uma rodada de validação, o que, por sua vez, impõe um grau mais alto de exatidão do programa.</span><span class="sxs-lookup"><span data-stu-id="f4087-115">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4087-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="f4087-116">See also</span></span>

- [<span data-ttu-id="f4087-117">Uniões discriminadas</span><span class="sxs-lookup"><span data-stu-id="f4087-117">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="f4087-118">Correspondência padrão</span><span class="sxs-lookup"><span data-stu-id="f4087-118">Pattern Matching</span></span>](pattern-matching.md)
