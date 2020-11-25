---
title: 'Alteração significativa: alteração de comportamento para vector2. Lerp e Vector4. Lerp'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que a implementação de vector2. Lerp e Vector4. Lerp mudou para uma conta correta para um erro de arredondamento de ponto flutuante.
ms.date: 11/01/2020
ms.openlocfilehash: 8e363a559dba8b7563c40637c47f101d59951216
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760343"
---
# <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="e7fa4-103">Alteração de comportamento para vector2. Lerp e Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="e7fa4-103">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="e7fa4-104">A implementação de <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> e <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> mudou para uma conta correta para um erro de arredondamento de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="e7fa4-104">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

## <a name="change-description"></a><span data-ttu-id="e7fa4-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="e7fa4-105">Change description</span></span>

<span data-ttu-id="e7fa4-106">Anteriormente, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> e <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> foram implementados como `value1 + (value2 - value1) * amount` .</span><span class="sxs-lookup"><span data-stu-id="e7fa4-106">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="e7fa4-107">No entanto, devido a um erro de arredondamento de ponto flutuante, esse algoritmo nem sempre retorna `value2` quando `amount` é `1.0f` .</span><span class="sxs-lookup"><span data-stu-id="e7fa4-107">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="e7fa4-108">No .NET 5,0 e posterior, a implementação usa o mesmo algoritmo que <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType> , que é `(value1 * (1.0f - amount)) + (value2 * amount)` .</span><span class="sxs-lookup"><span data-stu-id="e7fa4-108">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="e7fa4-109">Esse algoritmo conta corretamente para o erro de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="e7fa4-109">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="e7fa4-110">Agora, quando `amount` é `1.0f` , o resultado é precisamente `value2` .</span><span class="sxs-lookup"><span data-stu-id="e7fa4-110">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="e7fa4-111">O algoritmo atualizado também permite que o algoritmo seja otimizado livremente usando <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> quando ele está disponível.</span><span class="sxs-lookup"><span data-stu-id="e7fa4-111">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e7fa4-112">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="e7fa4-112">Version introduced</span></span>

<span data-ttu-id="e7fa4-113">5.0</span><span class="sxs-lookup"><span data-stu-id="e7fa4-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e7fa4-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="e7fa4-114">Recommended action</span></span>

<span data-ttu-id="e7fa4-115">Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="e7fa4-115">No action is necessary.</span></span> <span data-ttu-id="e7fa4-116">No entanto, se você quiser manter o comportamento antigo, poderá implementar sua própria `Lerp` função que usa o algoritmo anterior do `value1 + (value2 - value1) * amount` .</span><span class="sxs-lookup"><span data-stu-id="e7fa4-116">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e7fa4-117">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="e7fa4-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
