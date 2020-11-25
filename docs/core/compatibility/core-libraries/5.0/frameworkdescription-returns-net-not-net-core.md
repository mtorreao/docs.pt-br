---
title: 'Alteração significativa: o valor de FrameworkDescription é .NET, em vez de .NET Core'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que RuntimeInformation. FrameworkDescription agora retorna ".NET" em vez de ".NET Core".
ms.date: 11/01/2020
ms.openlocfilehash: 3925fb092135c26291e1e60b99f359974d21553c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760417"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="eddae-103">O valor de FrameworkDescription é .NET, em vez de .NET Core</span><span class="sxs-lookup"><span data-stu-id="eddae-103">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="eddae-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> agora retorna ".NET" em vez de ".NET Core".</span><span class="sxs-lookup"><span data-stu-id="eddae-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

## <a name="change-description"></a><span data-ttu-id="eddae-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="eddae-105">Change description</span></span>

<span data-ttu-id="eddae-106">Nas versões anteriores do .NET, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> retorna ".NET Core" como parte da cadeia de caracteres de descrição, por exemplo, `.NET Core 3.1.1` .</span><span class="sxs-lookup"><span data-stu-id="eddae-106">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="eddae-107">A partir do .NET 5,0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> retorna ".net" como parte da cadeia de caracteres de descrição, por exemplo, `.NET 5.0.0` .</span><span class="sxs-lookup"><span data-stu-id="eddae-107">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="eddae-108">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="eddae-108">Reason for change</span></span>

<span data-ttu-id="eddae-109">Com o .NET 5, `netcoreapp` é substituído pelo `net` como o moniker de estrutura de destino curto.</span><span class="sxs-lookup"><span data-stu-id="eddae-109">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="eddae-110">Para consistência, a descrição da estrutura também foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="eddae-110">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="eddae-111">A alteração é superficial, pois a `FrameworkName` não é codificada em nenhum outro lugar do que na <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> propriedade.</span><span class="sxs-lookup"><span data-stu-id="eddae-111">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="eddae-112">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="eddae-112">Version introduced</span></span>

<span data-ttu-id="eddae-113">5.0</span><span class="sxs-lookup"><span data-stu-id="eddae-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="eddae-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="eddae-114">Recommended action</span></span>

<span data-ttu-id="eddae-115">Atualize qualquer código que pesquise ".NET Core" na cadeia de caracteres retornada por <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> .</span><span class="sxs-lookup"><span data-stu-id="eddae-115">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="eddae-116">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="eddae-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
