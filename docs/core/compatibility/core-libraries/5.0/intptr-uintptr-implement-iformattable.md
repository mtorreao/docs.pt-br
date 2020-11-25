---
title: 'Alteração significativa: IntPtr e UIntPtr implementam IFormattable'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que IntPtr e UIntPtr agora implementam IFormattable.
ms.date: 11/01/2020
ms.openlocfilehash: 0684652cdc2b8cf1d237074263bf0809082b0dcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760506"
---
# <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="dafc5-103">IntPtr e UIntPtr implementam IFormattable</span><span class="sxs-lookup"><span data-stu-id="dafc5-103">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="dafc5-104"><xref:System.IntPtr> e <xref:System.UIntPtr> agora implemente <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="dafc5-104"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="dafc5-105">As funções que verificam o <xref:System.IFormattable> suporte agora podem retornar resultados diferentes para esses tipos, pois eles podem passar um especificador de formato e uma cultura.</span><span class="sxs-lookup"><span data-stu-id="dafc5-105">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

## <a name="change-description"></a><span data-ttu-id="dafc5-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="dafc5-106">Change description</span></span>

<span data-ttu-id="dafc5-107">Em versões anteriores do .NET, <xref:System.IntPtr> e <xref:System.UIntPtr> não implemente <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="dafc5-107">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="dafc5-108">As funções que verificam <xref:System.IFormattable> podem retornar a apenas chamar <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> ou <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType> , o que significa que especificadores de formato e culturas não são respeitados.</span><span class="sxs-lookup"><span data-stu-id="dafc5-108">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="dafc5-109">No .NET 5,0 e versões posteriores, <xref:System.IntPtr> e <xref:System.UIntPtr> implemente <xref:System.IFormattable> .</span><span class="sxs-lookup"><span data-stu-id="dafc5-109">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="dafc5-110">As funções que verificam o <xref:System.IFormattable> suporte agora podem retornar resultados diferentes para esses tipos, pois eles podem passar um especificador de formato e uma cultura.</span><span class="sxs-lookup"><span data-stu-id="dafc5-110">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="dafc5-111">Essa alteração afeta cenários como cadeias de caracteres interpoladas e <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> , entre outros.</span><span class="sxs-lookup"><span data-stu-id="dafc5-111">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="dafc5-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="dafc5-112">Reason for change</span></span>

<span data-ttu-id="dafc5-113"><xref:System.IntPtr> e <xref:System.UIntPtr> agora tem suporte a idiomas em C# por meio das `nint` `nuint` palavras-chave e.</span><span class="sxs-lookup"><span data-stu-id="dafc5-113"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="dafc5-114">Os tipos de suporte foram atualizados para fornecer paridade próxima (quando possível) com a funcionalidade exposta por outros tipos primitivos, como <xref:System.Int32?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="dafc5-114">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="dafc5-115">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="dafc5-115">Version introduced</span></span>

<span data-ttu-id="dafc5-116">5.0</span><span class="sxs-lookup"><span data-stu-id="dafc5-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="dafc5-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="dafc5-117">Recommended action</span></span>

<span data-ttu-id="dafc5-118">Se você não quiser que um especificador de formato ou cultura personalizada seja usado ao exibir valores desses tipos, você pode chamar o <xref:System.IntPtr.ToString?displayProperty=nameWithType> e <xref:System.UIntPtr.ToString?displayProperty=nameWithType> sobrecargas de `ToString()` .</span><span class="sxs-lookup"><span data-stu-id="dafc5-118">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="dafc5-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="dafc5-119">Affected APIs</span></span>

<span data-ttu-id="dafc5-120">Não detectável via análise de API.</span><span class="sxs-lookup"><span data-stu-id="dafc5-120">Not detectable via API analysis.</span></span>

<!--

### Category

Core .NET libraries

### Affected APIs

Not detectable via API analysis.

-->
