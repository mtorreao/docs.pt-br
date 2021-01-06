---
description: Palavra-chave public – Referência de C#
title: Palavra-chave public – Referência de C#
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 90c1d2a1d9efcdf57f914f4318bf7a743d3f37ec
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938462"
---
# <a name="public-c-reference"></a><span data-ttu-id="c6a27-103">public (Referência de C#)</span><span class="sxs-lookup"><span data-stu-id="c6a27-103">public (C# Reference)</span></span>

<span data-ttu-id="c6a27-104">A palavra-chave `public` é um modificador de acesso para tipos e membros de tipo.</span><span class="sxs-lookup"><span data-stu-id="c6a27-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="c6a27-105">Acesso público é o nível de acesso mais permissivo.</span><span class="sxs-lookup"><span data-stu-id="c6a27-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="c6a27-106">Não há nenhuma restrição quanto ao acesso a membros públicos, como neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="c6a27-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="c6a27-107">Consulte [Modificadores de acesso](../../programming-guide/classes-and-structs/access-modifiers.md) e [Níveis de acessibilidade](accessibility-levels.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6a27-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="c6a27-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c6a27-108">Example</span></span>

<span data-ttu-id="c6a27-109">No exemplo a seguir, duas classes são declaradas, `PointTest` e `Program`.</span><span class="sxs-lookup"><span data-stu-id="c6a27-109">In the following example, two classes are declared, `PointTest` and `Program`.</span></span> <span data-ttu-id="c6a27-110">Os membros públicos `x` e `y` de `PointTest` são acessados diretamente de `Program`.</span><span class="sxs-lookup"><span data-stu-id="c6a27-110">The public members `x` and `y` of `PointTest` are accessed directly from `Program`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="c6a27-111">Se alterar o nível de acesso de `public` para [particular](private.md) ou [protegido](protected.md), você receberá a mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="c6a27-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="c6a27-112">'PointTest.y' é inacessível devido ao seu nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="c6a27-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c6a27-113">Especificação da linguagem C#</span><span class="sxs-lookup"><span data-stu-id="c6a27-113">C# language specification</span></span>  

<span data-ttu-id="c6a27-114">Para obter mais informações, veja [Acessibilidade declarada](~/_csharplang/spec/basic-concepts.md#declared-accessibility) na [Especificação da Linguagem C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="c6a27-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c6a27-115">A especificação da linguagem é a fonte definitiva para a sintaxe e o uso de C#.</span><span class="sxs-lookup"><span data-stu-id="c6a27-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6a27-116">Veja também</span><span class="sxs-lookup"><span data-stu-id="c6a27-116">See also</span></span>

- [<span data-ttu-id="c6a27-117">Referência do C#</span><span class="sxs-lookup"><span data-stu-id="c6a27-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c6a27-118">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="c6a27-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c6a27-119">Modificadores de acesso</span><span class="sxs-lookup"><span data-stu-id="c6a27-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="c6a27-120">Palavras-chave do C#</span><span class="sxs-lookup"><span data-stu-id="c6a27-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c6a27-121">Modificadores de acesso</span><span class="sxs-lookup"><span data-stu-id="c6a27-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="c6a27-122">Níveis de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="c6a27-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="c6a27-123">Modificadores</span><span class="sxs-lookup"><span data-stu-id="c6a27-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="c6a27-124">pessoal</span><span class="sxs-lookup"><span data-stu-id="c6a27-124">private</span></span>](private.md)
- [<span data-ttu-id="c6a27-125">protegidos</span><span class="sxs-lookup"><span data-stu-id="c6a27-125">protected</span></span>](protected.md)
- [<span data-ttu-id="c6a27-126">interno</span><span class="sxs-lookup"><span data-stu-id="c6a27-126">internal</span></span>](internal.md)
