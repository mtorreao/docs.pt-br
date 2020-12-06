---
title: Expressões de objeto
description: 'Saiba como usar expressões de objeto F # quando quiser evitar o código extra e a sobrecarga necessárias para criar um novo tipo nomeado.'
ms.date: 02/08/2019
ms.openlocfilehash: 8a3e40b7833b551eefb95ec62b935acd1ba7b1f9
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740296"
---
# <a name="object-expressions"></a><span data-ttu-id="ade8c-103">Expressões de objeto</span><span class="sxs-lookup"><span data-stu-id="ade8c-103">Object Expressions</span></span>

<span data-ttu-id="ade8c-104">Uma *expressão de objeto* é uma expressão que cria uma nova instância de um tipo de objeto anônimo criado dinamicamente com base em um tipo base, interface ou conjunto de interfaces existente.</span><span class="sxs-lookup"><span data-stu-id="ade8c-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="ade8c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ade8c-105">Syntax</span></span>

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a><span data-ttu-id="ade8c-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="ade8c-106">Remarks</span></span>

<span data-ttu-id="ade8c-107">Na sintaxe anterior, o *TypeName* representa um tipo de classe ou de interface existente.</span><span class="sxs-lookup"><span data-stu-id="ade8c-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="ade8c-108">o *tipo-params* descreve os parâmetros de tipo genérico opcionais.</span><span class="sxs-lookup"><span data-stu-id="ade8c-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="ade8c-109">Os *argumentos* são usados somente para tipos de classe, que exigem parâmetros de construtor.</span><span class="sxs-lookup"><span data-stu-id="ade8c-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="ade8c-110">As *definições de membro* são substituições de métodos de classe base ou implementações de métodos abstratos de uma classe base ou de uma interface.</span><span class="sxs-lookup"><span data-stu-id="ade8c-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="ade8c-111">O exemplo a seguir ilustra vários tipos diferentes de expressões de objeto.</span><span class="sxs-lookup"><span data-stu-id="ade8c-111">The following example illustrates several different types of object expressions.</span></span>

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn $"{obj1}"

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a><span data-ttu-id="ade8c-112">Usando expressões de objeto</span><span class="sxs-lookup"><span data-stu-id="ade8c-112">Using Object Expressions</span></span>

<span data-ttu-id="ade8c-113">Você usa expressões de objeto quando deseja evitar o código extra e a sobrecarga necessária para criar um novo tipo nomeado.</span><span class="sxs-lookup"><span data-stu-id="ade8c-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="ade8c-114">Se você usar expressões de objeto para minimizar o número de tipos criados em um programa, poderá reduzir o número de linhas de código e evitar a proliferação desnecessária de tipos.</span><span class="sxs-lookup"><span data-stu-id="ade8c-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="ade8c-115">Em vez de criar vários tipos apenas para lidar com situações específicas, você pode usar uma expressão de objeto que personaliza um tipo existente ou fornece uma implementação apropriada de uma interface para o caso específico em questão.</span><span class="sxs-lookup"><span data-stu-id="ade8c-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="ade8c-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="ade8c-116">See also</span></span>

- [<span data-ttu-id="ade8c-117">Referência de linguagem F #</span><span class="sxs-lookup"><span data-stu-id="ade8c-117">F# Language Reference</span></span>](index.md)
