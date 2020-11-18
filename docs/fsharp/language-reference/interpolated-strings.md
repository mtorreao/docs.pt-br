---
title: Cadeias de caracteres interpoladas
description: 'Saiba mais sobre cadeias interpoladas, uma forma especial de cadeia de caracteres que permite inserir expressões F # diretamente dentro delas.'
ms.date: 11/12/2020
ms.openlocfilehash: a49d4e743306fd9bdabb1e019ec4e6c77e0e1f5a
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688594"
---
# <a name="interpolated-strings"></a><span data-ttu-id="0e4a4-103">Cadeias de caracteres interpoladas</span><span class="sxs-lookup"><span data-stu-id="0e4a4-103">Interpolated strings</span></span>

<span data-ttu-id="0e4a4-104">Cadeias de caracteres interpoladas são [cadeias de caracteres](strings.md) que permitem inserir expressões F # nelas.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-104">Interpolated strings are [strings](strings.md) that allow you to embed F# expressions into them.</span></span> <span data-ttu-id="0e4a4-105">Eles são úteis em uma ampla gama de cenários em que o valor de uma cadeia de caracteres pode ser alterado com base no resultado de um valor ou expressão.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-105">They are helpful in a wide range of scenarios where the value of a string may change based on the result of a value or expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e4a4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0e4a4-106">Syntax</span></span>

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a><span data-ttu-id="0e4a4-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="0e4a4-107">Remarks</span></span>

<span data-ttu-id="0e4a4-108">As cadeias de caracteres interpoladas permitem escrever código em "buracos" dentro de um literal de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-108">Interpolated strings let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="0e4a4-109">Este é um exemplo básico:</span><span class="sxs-lookup"><span data-stu-id="0e4a4-109">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="0e4a4-110">O conteúdo entre cada `{}` par de chaves pode ser qualquer expressão F #.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-110">The contents in between each `{}` brace pair can be any F# expression.</span></span>

<span data-ttu-id="0e4a4-111">Para escapar de um `{}` par de chaves, escreva dois deles da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0e4a4-111">To escape a `{}` brace pair, write two of them like so:</span></span>

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a><span data-ttu-id="0e4a4-112">Cadeias de caracteres interpoladas com tipo</span><span class="sxs-lookup"><span data-stu-id="0e4a4-112">Typed interpolated strings</span></span>

<span data-ttu-id="0e4a4-113">As cadeias de caracteres interpoladas também podem ter especificadores de formato F # para impor o tipo seguro.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-113">Interpolated strings can also have F# format specifiers to enforce type safey.</span></span>

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="0e4a4-114">No exemplo anterior, o código transmite erroneamente o `age` valor onde `name` deveria ser, e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-114">In the previous example, the code mistakenly passes the `age` value where `name` should be, and vice/versa.</span></span> <span data-ttu-id="0e4a4-115">Como as cadeias de caracteres interpoladas usam especificadores de formato, esse é um erro de compilação em vez de um bug de tempo de execução sutil.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-115">Because the interpolated strings use format specifiers, this is a compile error instead of a subtle runtime bug.</span></span>

<span data-ttu-id="0e4a4-116">Todos os especificadores de formato abordados na [formatação de texto sem formatação](plaintext-formatting.md) são válidos dentro de uma cadeia de caracteres interpolada.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-116">All format specifiers covered in [plaintext formatting](plaintext-formatting.md) are valid inside of an interpolated string.</span></span>

## <a name="verbatim-interpolated-strings"></a><span data-ttu-id="0e4a4-117">Cadeias de caracteres interpoladas literalmente</span><span class="sxs-lookup"><span data-stu-id="0e4a4-117">Verbatim interpolated strings</span></span>

<span data-ttu-id="0e4a4-118">O F # dá suporte a cadeias de caracteres interpoladas literalmente com aspas triplas para que você possa inserir literais de cadeia.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-118">F# supports verbatim interpolated strings with triple quotes so that you can embed string literals.</span></span>

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a><span data-ttu-id="0e4a4-119">Alinhando expressões em cadeias de caracteres interpoladas</span><span class="sxs-lookup"><span data-stu-id="0e4a4-119">Aligning expressions in interpolated strings</span></span>

<span data-ttu-id="0e4a4-120">Você pode alinhar as expressões à esquerda ou alinhadas à direita dentro de cadeias interpoladas com `|` e uma especificação de quantos espaços.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-120">You can left-align or right-align expressions inside interpolated strings with `|` and a specification of how many spaces.</span></span> <span data-ttu-id="0e4a4-121">A cadeia de caracteres interpolada a seguir alinha as expressões esquerda e direita à esquerda e à direita, respectivamente, por 7 espaços.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-121">The following interpolated string aligns the left and right expressions to the left and right, respectively, by 7  spaces.</span></span>

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a><span data-ttu-id="0e4a4-122">Cadeias de caracteres interpoladas e `FormattableString` formatação</span><span class="sxs-lookup"><span data-stu-id="0e4a4-122">Interpolated strings and `FormattableString` formatting</span></span>

<span data-ttu-id="0e4a4-123">Você também pode aplicar a formatação que segue as regras para <xref:System.FormattableString> :</span><span class="sxs-lookup"><span data-stu-id="0e4a4-123">You can also apply formatting that adheres to the rules for <xref:System.FormattableString>:</span></span>

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

<span data-ttu-id="0e4a4-124">Além disso, uma cadeia de caracteres interpolada também pode ser typechecked <xref:System.FormattableString> por meio de uma anotação de tipo:</span><span class="sxs-lookup"><span data-stu-id="0e4a4-124">Additionally, an interpolated string can also be typechecked as a <xref:System.FormattableString> via a type annotation:</span></span>

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

<span data-ttu-id="0e4a4-125">Observe que a anotação de tipo deve estar na própria expressão de cadeia de caracteres interpolada.</span><span class="sxs-lookup"><span data-stu-id="0e4a4-125">Note that the type annotation must be on the interpolated string expression itself.</span></span> <span data-ttu-id="0e4a4-126">O F # não converte implicitamente uma cadeia de caracteres interpolada em um <xref:System.FormattableString> .</span><span class="sxs-lookup"><span data-stu-id="0e4a4-126">F# does not implicitly convert an interpolated string into a <xref:System.FormattableString>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e4a4-127">Veja também</span><span class="sxs-lookup"><span data-stu-id="0e4a4-127">See also</span></span>

* [<span data-ttu-id="0e4a4-128">Cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="0e4a4-128">Strings</span></span>](strings.md)
