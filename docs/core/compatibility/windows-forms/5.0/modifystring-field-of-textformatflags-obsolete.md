---
title: 'Alteração significativa: TextFormatFlags. Modifystring é obsoleto'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que o campo TextFormatFlags. Modifystring está obsoleto como um aviso.
ms.date: 11/05/2020
ms.openlocfilehash: 83dca65a770ccdcd5ce48bb669f5122dc2d5ad77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760352"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="2ba96-103">TextFormatFlags. Modifystring é obsoleto</span><span class="sxs-lookup"><span data-stu-id="2ba96-103">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="2ba96-104">O <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> campo é obsoleto, como um aviso, e pode ser removido em uma versão futura do .net.</span><span class="sxs-lookup"><span data-stu-id="2ba96-104">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

## <a name="change-description"></a><span data-ttu-id="2ba96-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="2ba96-105">Change description</span></span>

<span data-ttu-id="2ba96-106">Nas versões anteriores do .NET, o <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> campo de enumeração não está marcado como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2ba96-106">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="2ba96-107">No .NET 5,0 e versões posteriores, ele é marcado como obsoleto como um aviso.</span><span class="sxs-lookup"><span data-stu-id="2ba96-107">In .NET 5.0 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="2ba96-108">Esse campo pode ser removido em uma versão futura do .NET.</span><span class="sxs-lookup"><span data-stu-id="2ba96-108">This field may be removed in a future .NET version.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2ba96-109">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="2ba96-109">Reason for change</span></span>

<span data-ttu-id="2ba96-110">Passar uma cadeia de caracteres para <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> com <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> altera a cadeia de caracteres em algumas situações.</span><span class="sxs-lookup"><span data-stu-id="2ba96-110">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="2ba96-111">Esse comportamento interrompe a promessa de imutabilidade da cadeia de caracteres e pode levar a uma corrupção fatal do estado do tempo de execução .NET.</span><span class="sxs-lookup"><span data-stu-id="2ba96-111">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2ba96-112">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="2ba96-112">Version introduced</span></span>

<span data-ttu-id="2ba96-113">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="2ba96-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2ba96-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="2ba96-114">Recommended action</span></span>

<span data-ttu-id="2ba96-115">Atualize qualquer código que dependa de <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2ba96-115">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2ba96-116">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="2ba96-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->
