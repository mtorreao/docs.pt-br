---
title: Extensões de tipo
description: 'Saiba como as extensões de tipo F # permitem adicionar novos membros a um tipo de objeto definido anteriormente.'
ms.date: 02/05/2020
ms.openlocfilehash: c9adddb3133a4af57a12be0b09c22954a8bff6a7
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2020
ms.locfileid: "97737262"
---
# <a name="type-extensions"></a><span data-ttu-id="27c18-103">Extensões de tipo</span><span class="sxs-lookup"><span data-stu-id="27c18-103">Type extensions</span></span>

<span data-ttu-id="27c18-104">Extensões de tipo (também chamadas de _aumentos_) são uma família de recursos que permitem adicionar novos membros a um tipo de objeto definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="27c18-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="27c18-105">Os três recursos são:</span><span class="sxs-lookup"><span data-stu-id="27c18-105">The three features are:</span></span>

- <span data-ttu-id="27c18-106">Extensões de tipo intrínseco</span><span class="sxs-lookup"><span data-stu-id="27c18-106">Intrinsic type extensions</span></span>
- <span data-ttu-id="27c18-107">Extensões de tipo opcionais</span><span class="sxs-lookup"><span data-stu-id="27c18-107">Optional type extensions</span></span>
- <span data-ttu-id="27c18-108">Métodos de extensão</span><span class="sxs-lookup"><span data-stu-id="27c18-108">Extension methods</span></span>

<span data-ttu-id="27c18-109">Cada um pode ser usado em diferentes cenários e tem compensações diferentes.</span><span class="sxs-lookup"><span data-stu-id="27c18-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="27c18-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="27c18-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [<Extension>]
    static member extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="27c18-111">Extensões de tipo intrínseco</span><span class="sxs-lookup"><span data-stu-id="27c18-111">Intrinsic type extensions</span></span>

<span data-ttu-id="27c18-112">Uma extensão de tipo intrínseco é uma extensão de tipo que estende um tipo definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="27c18-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="27c18-113">As extensões de tipo intrínseco devem ser definidas no mesmo arquivo **e** no mesmo namespace ou módulo que o tipo que está sendo estendido.</span><span class="sxs-lookup"><span data-stu-id="27c18-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="27c18-114">Qualquer outra definição fará com que elas sejam [extensões de tipo opcionais](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="27c18-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="27c18-115">As extensões de tipo intrínseco, às vezes, são uma maneira mais limpa de separar a funcionalidade da declaração de tipo.</span><span class="sxs-lookup"><span data-stu-id="27c18-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="27c18-116">O exemplo a seguir mostra como definir uma extensão de tipo intrínseco:</span><span class="sxs-lookup"><span data-stu-id="27c18-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="27c18-117">O uso de uma extensão de tipo permite que você separe cada uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="27c18-117">Using a type extension allows you to separate each of the following:</span></span>

- <span data-ttu-id="27c18-118">A declaração de um `Variant` tipo</span><span class="sxs-lookup"><span data-stu-id="27c18-118">The declaration of a `Variant` type</span></span>
- <span data-ttu-id="27c18-119">Funcionalidade para imprimir a `Variant` classe dependendo de sua "forma"</span><span class="sxs-lookup"><span data-stu-id="27c18-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
- <span data-ttu-id="27c18-120">Uma maneira de acessar a funcionalidade de impressão com a notação de estilo de objeto `.`</span><span class="sxs-lookup"><span data-stu-id="27c18-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="27c18-121">Essa é uma alternativa à definição de tudo como um membro `Variant` .</span><span class="sxs-lookup"><span data-stu-id="27c18-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="27c18-122">Embora não seja uma abordagem inerentemente melhor, pode ser uma representação mais limpa da funcionalidade em algumas situações.</span><span class="sxs-lookup"><span data-stu-id="27c18-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="27c18-123">As extensões de tipo intrínseco são compiladas como membros do tipo que aumentam e aparecem no tipo quando o tipo é examinado por reflexão.</span><span class="sxs-lookup"><span data-stu-id="27c18-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="27c18-124">Extensões de tipo opcionais</span><span class="sxs-lookup"><span data-stu-id="27c18-124">Optional type extensions</span></span>

<span data-ttu-id="27c18-125">Uma extensão de tipo opcional é uma extensão que aparece fora do módulo, namespace ou assembly original do tipo que está sendo estendido.</span><span class="sxs-lookup"><span data-stu-id="27c18-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="27c18-126">Extensões de tipo opcional são úteis para estender um tipo que você não definiu por conta própria.</span><span class="sxs-lookup"><span data-stu-id="27c18-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="27c18-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="27c18-127">For example:</span></span>

```fsharp
module Extensions

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for _ in 1 .. n -> x
        }
```

<span data-ttu-id="27c18-128">Agora você pode acessar `RepeatElements` como se fosse membro do, desde que <xref:System.Collections.Generic.IEnumerable%601> o `Extensions` módulo seja aberto no escopo no qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="27c18-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="27c18-129">As extensões opcionais não aparecem no tipo estendido quando examinadas por reflexão.</span><span class="sxs-lookup"><span data-stu-id="27c18-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="27c18-130">As extensões opcionais devem estar em módulos e só estão no escopo quando o módulo que contém a extensão está aberto ou está no escopo.</span><span class="sxs-lookup"><span data-stu-id="27c18-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="27c18-131">Membros de extensão opcionais são compilados para membros estáticos para os quais a instância do objeto é passada implicitamente como o primeiro parâmetro.</span><span class="sxs-lookup"><span data-stu-id="27c18-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="27c18-132">No entanto, eles atuam como se fossem membros de instância ou membros estáticos de acordo com o modo como eles são declarados.</span><span class="sxs-lookup"><span data-stu-id="27c18-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

<span data-ttu-id="27c18-133">Os membros de extensão opcionais também não são visíveis para os consumidores do C# ou do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="27c18-133">Optional extension members are also not visible to C# or Visual Basic consumers.</span></span> <span data-ttu-id="27c18-134">Eles só podem ser consumidos em outro código F #.</span><span class="sxs-lookup"><span data-stu-id="27c18-134">They can only be consumed in other F# code.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="27c18-135">Limitação genérica de extensões de tipo intrínsecas e opcionais</span><span class="sxs-lookup"><span data-stu-id="27c18-135">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="27c18-136">É possível declarar uma extensão de tipo em um tipo genérico em que a variável de tipo é restrita.</span><span class="sxs-lookup"><span data-stu-id="27c18-136">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="27c18-137">O requisito é que a restrição da declaração de extensão corresponda à restrição do tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="27c18-137">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="27c18-138">No entanto, mesmo quando as restrições são correspondidas entre um tipo declarado e uma extensão de tipo, é possível que uma restrição seja inferida pelo corpo de um membro estendido que impõe um requisito diferente no parâmetro de tipo do que o tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="27c18-138">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="27c18-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="27c18-139">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="27c18-140">Não há como obter esse código para trabalhar com uma extensão de tipo opcional:</span><span class="sxs-lookup"><span data-stu-id="27c18-140">There is no way to get this code to work with an optional type extension:</span></span>

- <span data-ttu-id="27c18-141">Como está, o `Sum` membro tem uma restrição diferente em `'T` ( `static member get_Zero` e `static member (+)` ) do que a extensão de tipo define.</span><span class="sxs-lookup"><span data-stu-id="27c18-141">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
- <span data-ttu-id="27c18-142">A modificação da extensão de tipo para ter a mesma restrição que `Sum` não corresponderá mais à restrição definida em `IEnumerable<'T>` .</span><span class="sxs-lookup"><span data-stu-id="27c18-142">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
- <span data-ttu-id="27c18-143">Alterar `member this.Sum` para `member inline this.Sum` dará um erro informando que as restrições de tipo são incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="27c18-143">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="27c18-144">O que é desejado são métodos estáticos que "flutuam no espaço" e podem ser apresentados como se estivessem estendendo um tipo.</span><span class="sxs-lookup"><span data-stu-id="27c18-144">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="27c18-145">É aí que os métodos de extensão se tornam necessários.</span><span class="sxs-lookup"><span data-stu-id="27c18-145">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="27c18-146">Métodos de extensão</span><span class="sxs-lookup"><span data-stu-id="27c18-146">Extension methods</span></span>

<span data-ttu-id="27c18-147">Por fim, os métodos de extensão (às vezes chamados de "membros de extensão de estilo C#") podem ser declarados em F # como um método de membro estático em uma classe.</span><span class="sxs-lookup"><span data-stu-id="27c18-147">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="27c18-148">Os métodos de extensão são úteis para quando você deseja definir extensões em um tipo genérico que restringirá a variável de tipo.</span><span class="sxs-lookup"><span data-stu-id="27c18-148">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="27c18-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="27c18-149">For example:</span></span>

```fsharp
namespace Extensions

open System.Collections.Generic
open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="27c18-150">Quando usado, esse código fará com que ele apareça como se `Sum` estiver definido em <xref:System.Collections.Generic.IEnumerable%601> , desde que `Extensions` tenha sido aberto ou esteja no escopo.</span><span class="sxs-lookup"><span data-stu-id="27c18-150">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

<span data-ttu-id="27c18-151">Para que a extensão esteja disponível para o código VB.NET, `ExtensionAttribute` é necessário um extra no nível do assembly:</span><span class="sxs-lookup"><span data-stu-id="27c18-151">For the extension to be available to VB.NET code, an extra `ExtensionAttribute` is required at the assembly level:</span></span>

```fsharp
module AssemblyInfo
open System.Runtime.CompilerServices
[<assembly:Extension>]
do ()
```

## <a name="other-remarks"></a><span data-ttu-id="27c18-152">Outros comentários</span><span class="sxs-lookup"><span data-stu-id="27c18-152">Other remarks</span></span>

<span data-ttu-id="27c18-153">As extensões de tipo também têm os seguintes atributos:</span><span class="sxs-lookup"><span data-stu-id="27c18-153">Type extensions also have the following attributes:</span></span>

- <span data-ttu-id="27c18-154">Qualquer tipo que possa ser acessado pode ser estendido.</span><span class="sxs-lookup"><span data-stu-id="27c18-154">Any type that can be accessed can be extended.</span></span>
- <span data-ttu-id="27c18-155">Extensões intrínsecas e opcionais de tipo podem definir _qualquer_ tipo de membro, não apenas métodos.</span><span class="sxs-lookup"><span data-stu-id="27c18-155">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="27c18-156">Portanto, as propriedades de extensão também são possíveis, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="27c18-156">So extension properties are also possible, for example.</span></span>
- <span data-ttu-id="27c18-157">O `self-identifier` token na [sintaxe](type-extensions.md#syntax) representa a instância do tipo que está sendo invocado, assim como os membros comuns.</span><span class="sxs-lookup"><span data-stu-id="27c18-157">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
- <span data-ttu-id="27c18-158">Os membros estendidos podem ser membros estáticos ou de instância.</span><span class="sxs-lookup"><span data-stu-id="27c18-158">Extended members can be static or instance members.</span></span>
- <span data-ttu-id="27c18-159">Variáveis de tipo em uma extensão de tipo devem corresponder às restrições do tipo declarado.</span><span class="sxs-lookup"><span data-stu-id="27c18-159">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="27c18-160">As seguintes limitações também existem para extensões de tipo:</span><span class="sxs-lookup"><span data-stu-id="27c18-160">The following limitations also exist for type extensions:</span></span>

- <span data-ttu-id="27c18-161">As extensões de tipo não dão suporte a métodos virtuais ou abstratos.</span><span class="sxs-lookup"><span data-stu-id="27c18-161">Type extensions do not support virtual or abstract methods.</span></span>
- <span data-ttu-id="27c18-162">As extensões de tipo não oferecem suporte a métodos de substituição como aumentos.</span><span class="sxs-lookup"><span data-stu-id="27c18-162">Type extensions do not support override methods as augmentations.</span></span>
- <span data-ttu-id="27c18-163">As extensões de tipo não dão suporte a [parâmetros de tipo resolvidos estaticamente](./generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="27c18-163">Type extensions do not support [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>
- <span data-ttu-id="27c18-164">Extensões de tipo opcional não dão suporte a construtores como aumentos.</span><span class="sxs-lookup"><span data-stu-id="27c18-164">Optional Type extensions do not support constructors as augmentations.</span></span>
- <span data-ttu-id="27c18-165">Extensões de tipo não podem ser definidas em [abreviações de tipo](type-abbreviations.md).</span><span class="sxs-lookup"><span data-stu-id="27c18-165">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
- <span data-ttu-id="27c18-166">Extensões de tipo não são válidas para `byref<'T>` (embora possam ser declaradas).</span><span class="sxs-lookup"><span data-stu-id="27c18-166">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
- <span data-ttu-id="27c18-167">Extensões de tipo não são válidas para atributos (embora possam ser declaradas).</span><span class="sxs-lookup"><span data-stu-id="27c18-167">Type extensions are not valid for attributes (though they can be declared).</span></span>
- <span data-ttu-id="27c18-168">Você pode definir extensões que sobrecarregam outros métodos de mesmo nome, mas o compilador F # dá preferência a métodos que não são de extensão se houver uma chamada ambígua.</span><span class="sxs-lookup"><span data-stu-id="27c18-168">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="27c18-169">Por fim, se existirem várias extensões de tipo intrínsecos para um tipo, todos os membros deverão ser exclusivos.</span><span class="sxs-lookup"><span data-stu-id="27c18-169">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="27c18-170">Para extensões de tipo opcionais, os membros em extensões de tipo diferentes para o mesmo tipo podem ter os mesmos nomes.</span><span class="sxs-lookup"><span data-stu-id="27c18-170">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="27c18-171">Os erros de ambiguidade ocorrem somente se o código do cliente abrir dois escopos diferentes que definem os mesmos nomes de membro.</span><span class="sxs-lookup"><span data-stu-id="27c18-171">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="27c18-172">Veja também</span><span class="sxs-lookup"><span data-stu-id="27c18-172">See also</span></span>

- [<span data-ttu-id="27c18-173">Referência de linguagem F #</span><span class="sxs-lookup"><span data-stu-id="27c18-173">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="27c18-174">Membros</span><span class="sxs-lookup"><span data-stu-id="27c18-174">Members</span></span>](./members/index.md)
