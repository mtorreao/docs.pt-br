---
title: 'Alteração significativa: MulticastOption. Group não aceita um valor nulo'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que MulticastOption. Group não aceita mais um valor nulo.
ms.date: 08/18/2020
ms.openlocfilehash: 164ac8c2c8dd14f9e0758017e54eeb377f88a7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760357"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="22fb5-103">MulticastOption. Group não aceita um valor nulo</span><span class="sxs-lookup"><span data-stu-id="22fb5-103">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="22fb5-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> Não aceita mais um valor de `null` .</span><span class="sxs-lookup"><span data-stu-id="22fb5-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="22fb5-105">Se você definir a propriedade como `null` , um <xref:System.ArgumentNullException> será gerado.</span><span class="sxs-lookup"><span data-stu-id="22fb5-105">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="22fb5-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="22fb5-106">Version introduced</span></span>

<span data-ttu-id="22fb5-107">5.0</span><span class="sxs-lookup"><span data-stu-id="22fb5-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="22fb5-108">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="22fb5-108">Change description</span></span>

<span data-ttu-id="22fb5-109">Nas versões anteriores do .NET, você pode definir a <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> propriedade como `null` .</span><span class="sxs-lookup"><span data-stu-id="22fb5-109">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="22fb5-110">Se o <xref:System.Net.Sockets.MulticastOption> for passado posteriormente para <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> , o tempo de execução lançará um <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="22fb5-110">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="22fb5-111">No .NET 5,0 e posterior, um <xref:System.ArgumentNullException> será gerado se você definir a propriedade como `null` .</span><span class="sxs-lookup"><span data-stu-id="22fb5-111">In .NET 5.0 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="22fb5-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="22fb5-112">Reason for change</span></span>

<span data-ttu-id="22fb5-113">Para ser consistente com as diretrizes de design de estrutura, a propriedade foi atualizada para lançar um <xref:System.ArgumentNullException> se o valor for `null` .</span><span class="sxs-lookup"><span data-stu-id="22fb5-113">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="22fb5-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="22fb5-114">Recommended action</span></span>

<span data-ttu-id="22fb5-115">Certifique-se de que você não definiu <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> como `null` .</span><span class="sxs-lookup"><span data-stu-id="22fb5-115">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="22fb5-116">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="22fb5-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
