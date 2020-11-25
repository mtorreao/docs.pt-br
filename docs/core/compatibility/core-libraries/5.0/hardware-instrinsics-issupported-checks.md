---
title: 'Alteração significativa: verificações IsSupported de hardware intrínsecas podem diferir para tipos aninhados'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que a verificação de x64. Issupportd para intrínsecos de hardware agora pode produzir um resultado diferente.
ms.date: 11/01/2020
ms.openlocfilehash: 9acef15860de76a9743621cb4c5edba5aac3931c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760415"
---
# <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a><span data-ttu-id="534e4-103">Verificações IsSupported de hardware intrínsecas podem diferir para tipos aninhados</span><span class="sxs-lookup"><span data-stu-id="534e4-103">Hardware intrinsic IsSupported checks may differ for nested types</span></span>

<span data-ttu-id="534e4-104">A verificação `<Isa>.X64.IsSupported` , em que `<Isa>` se refere às classes no <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> namespace, agora pode produzir um resultado diferente para versões anteriores do .net.</span><span class="sxs-lookup"><span data-stu-id="534e4-104">Checking `<Isa>.X64.IsSupported`, where `<Isa>` refers to the classes in the <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> namespace, may now produce a different result to previous versions of .NET.</span></span>

> [!TIP]
> <span data-ttu-id="534e4-105">O *ISA* significa arquitetura padrão do setor.</span><span class="sxs-lookup"><span data-stu-id="534e4-105">*ISA* stands for industry standard architecture.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="534e4-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="534e4-106">Version introduced</span></span>

<span data-ttu-id="534e4-107">5.0</span><span class="sxs-lookup"><span data-stu-id="534e4-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="534e4-108">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="534e4-108">Change description</span></span>

<span data-ttu-id="534e4-109">Nas versões anteriores do .NET, alguns dos <xref:System.Runtime.Intrinsics.X86> tipos intrínsecos a hardware, por exemplo,, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType> não expõevam uma `X64` classe aninhada.</span><span class="sxs-lookup"><span data-stu-id="534e4-109">In previous versions of .NET, some of the <xref:System.Runtime.Intrinsics.X86> hardware-intrinsic types, for example, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, didn't expose a nested `X64` class.</span></span> <span data-ttu-id="534e4-110">Para esses tipos, chamar `<Isa>.X64.IsSupported` resolvido para uma `IsSupported` propriedade em uma classe aninhada `X64` de uma classe pai de `<Isa>` .</span><span class="sxs-lookup"><span data-stu-id="534e4-110">For these types, calling `<Isa>.X64.IsSupported` resolved to an `IsSupported` property on a nested `X64` class of a parent class of `<Isa>`.</span></span> <span data-ttu-id="534e4-111">Isso significava que a propriedade poderia retornar `true` mesmo quando `<Isa>.IsSupported` retorna `false` .</span><span class="sxs-lookup"><span data-stu-id="534e4-111">This meant that the property could return `true` even when `<Isa>.IsSupported` returns `false`.</span></span>

<span data-ttu-id="534e4-112">No .NET 5,0 e versões posteriores, todos os <xref:System.Runtime.Intrinsics.X86> tipos expõem uma `X64` classe aninhada que relata adequadamente o suporte.</span><span class="sxs-lookup"><span data-stu-id="534e4-112">In .NET 5.0 and later versions, all of the <xref:System.Runtime.Intrinsics.X86> types expose a nested `X64` class that appropriately reports support.</span></span> <span data-ttu-id="534e4-113">Isso garante que a hierarquia geral permaneça correta e que `<Isa>.X64.IsSupported` , se for `true` , `<Isa>.IsSupported` também possa ser considerada `true` .</span><span class="sxs-lookup"><span data-stu-id="534e4-113">This ensures that the general hierarchy remains correct, and that if `<Isa>.X64.IsSupported` is `true`, then `<Isa>.IsSupported` can also be assumed to be `true`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="534e4-114">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="534e4-114">Reason for change</span></span>

<span data-ttu-id="534e4-115">A intenção era que `<Isa>.X64.IsSupported` , se estiver `true` , `<Isa>.IsSupported` também esteja implícita `true` .</span><span class="sxs-lookup"><span data-stu-id="534e4-115">It was intended that if `<Isa>.X64.IsSupported` is `true`, `<Isa>.IsSupported` is also implied to be `true`.</span></span> <span data-ttu-id="534e4-116">No entanto, devido à forma como a resolução de membros funciona em C#, as classes que não tinham uma classe aninhada apresentaram `X64` uma situação em que isso não era sempre o caso e levou a bugs no código do usuário.</span><span class="sxs-lookup"><span data-stu-id="534e4-116">However, due to how member resolution works in C#, classes that didn't have a nested `X64` class exposed a situation where this wasn't always the case and led to bugs in user code.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="534e4-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="534e4-117">Recommended action</span></span>

<span data-ttu-id="534e4-118">Se necessário, ajuste o código que verifica `IsSupported` para verificar o ISA apropriado.</span><span class="sxs-lookup"><span data-stu-id="534e4-118">If necessary, adjust code that checks `IsSupported` to check for the appropriate ISA.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="534e4-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="534e4-119">Affected APIs</span></span>

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
