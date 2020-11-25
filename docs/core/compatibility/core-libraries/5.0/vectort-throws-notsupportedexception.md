---
title: 'Alteração significativa: vetor <T> gera NotSupportedException'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que <T> o vetor sempre gera uma exceção para parâmetros de tipo sem suporte.
ms.date: 11/01/2020
ms.openlocfilehash: 63db7c6b720735b180ed11098227b31a14008f74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760396"
---
# <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="06b72-103">Vetor \<T> sempre gera NotSupportedException para tipos sem suporte</span><span class="sxs-lookup"><span data-stu-id="06b72-103">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="06b72-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> Agora sempre gera um <xref:System.NotSupportedException> para parâmetros de tipo sem suporte.</span><span class="sxs-lookup"><span data-stu-id="06b72-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

## <a name="change-description"></a><span data-ttu-id="06b72-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="06b72-105">Change description</span></span>

<span data-ttu-id="06b72-106">Anteriormente, os membros de <xref:System.Numerics.Vector%601> nem sempre geraram um <xref:System.NotSupportedException> quando `T` era um [tipo sem suporte](#unsupported-types).</span><span class="sxs-lookup"><span data-stu-id="06b72-106">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="06b72-107">A exceção nem sempre foi acionada devido a caminhos de código com suporte para aceleração de hardware.</span><span class="sxs-lookup"><span data-stu-id="06b72-107">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="06b72-108">Por exemplo, `Vector<bool> + Vector<bool>` retornado `default` em vez de lançar uma exceção em plataformas que não têm aceleração de hardware, como ARM32.</span><span class="sxs-lookup"><span data-stu-id="06b72-108">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="06b72-109">Para tipos sem suporte, <xref:System.Numerics.Vector%601> os membros exibiram comportamento inconsistente em diferentes plataformas e configurações de hardware.</span><span class="sxs-lookup"><span data-stu-id="06b72-109">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="06b72-110">A partir do .NET 5,0, <xref:System.Numerics.Vector%601> os membros sempre lançam um <xref:System.NotSupportedException> em todas as configurações de hardware quando `T` não é um tipo com suporte.</span><span class="sxs-lookup"><span data-stu-id="06b72-110">Starting in .NET 5.0, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

### <a name="unsupported-types"></a><span data-ttu-id="06b72-111">Tipos sem suporte</span><span class="sxs-lookup"><span data-stu-id="06b72-111">Unsupported types</span></span>

<span data-ttu-id="06b72-112">Os tipos com suporte para o parâmetro de tipo de <xref:System.Numerics.Vector%601> são:</span><span class="sxs-lookup"><span data-stu-id="06b72-112">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

<span data-ttu-id="06b72-113">Os tipos com suporte não foram alterados, no entanto, eles podem ser alterados no futuro.</span><span class="sxs-lookup"><span data-stu-id="06b72-113">The supported types have not changed, however, they may change in the future.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="06b72-114">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="06b72-114">Version introduced</span></span>

<span data-ttu-id="06b72-115">5.0</span><span class="sxs-lookup"><span data-stu-id="06b72-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="06b72-116">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="06b72-116">Recommended action</span></span>

<span data-ttu-id="06b72-117">Não use um tipo sem suporte para o parâmetro de tipo de <xref:System.Numerics.Vector%601> .</span><span class="sxs-lookup"><span data-stu-id="06b72-117">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="06b72-118">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="06b72-118">Affected APIs</span></span>

- <span data-ttu-id="06b72-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> e todos os seus membros</span><span class="sxs-lookup"><span data-stu-id="06b72-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Category

Core .NET libraries

### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
