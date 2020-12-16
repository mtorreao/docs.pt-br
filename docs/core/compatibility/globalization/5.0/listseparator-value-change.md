---
title: 'Alteração significativa: alteração de valor de TextInfo. ListSeparator'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em que o valor padrão de TextInfo. ListSeparator foi alterado entre as versões 5,0 e 5.0.1.
ms.date: 12/10/2020
ms.openlocfilehash: 720d46c1908bcd70812f575a90f580470dbc7f32
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596452"
---
# <a name="textinfolistseparator-values-changed"></a><span data-ttu-id="6a322-103">Valores de TextInfo. ListSeparator alterados</span><span class="sxs-lookup"><span data-stu-id="6a322-103">TextInfo.ListSeparator values changed</span></span>

<span data-ttu-id="6a322-104">Os <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> valores padrão para culturas diferentes foram alterados em todos os sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="6a322-104">The default <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for different cultures have changed on all operating systems.</span></span>

## <a name="change-description"></a><span data-ttu-id="6a322-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="6a322-105">Change description</span></span>

<span data-ttu-id="6a322-106">No .NET 5.0.0, como parte da [mudança do NLS para bibliotecas ICU](icu-globalization-api.md), os valores padrão <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para diferentes culturas são alterados no Windows.</span><span class="sxs-lookup"><span data-stu-id="6a322-106">In .NET 5.0.0, as part of the [switch from NLS to ICU libraries](icu-globalization-api.md), the default <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for different cultures changed on Windows.</span></span> <span data-ttu-id="6a322-107">Os valores de separador decimal, obtidos de componentes internacionais para Unicode (ICU), foram usados como <xref:System.Globalization.TextInfo.ListSeparator> valores.</span><span class="sxs-lookup"><span data-stu-id="6a322-107">Decimal separator values, obtained from International Components for Unicode (ICU), were used as the <xref:System.Globalization.TextInfo.ListSeparator> values.</span></span> <span data-ttu-id="6a322-108">No Linux e no macOS, não havia nenhuma alteração nos <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> valores; ou seja, eles continuaram a usar valores de separadores decimais.</span><span class="sxs-lookup"><span data-stu-id="6a322-108">On Linux and macOS, there was no change in <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values; that is, they continued to use decimal separator values.</span></span>

<span data-ttu-id="6a322-109">Para todos os sistemas operacionais no .NET 5.0.1 e versões posteriores, os valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> são equivalentes aos valores que seriam obtidos do NLS.</span><span class="sxs-lookup"><span data-stu-id="6a322-109">For all operating systems in .NET 5.0.1 and later versions, the values for <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> are equivalent to the values that would be obtained from NLS.</span></span> <span data-ttu-id="6a322-110">Para o Windows, isso significa que os valores são equivalentes ao que estavam em .NET Framework e no .NET Core 1,0-3,1.</span><span class="sxs-lookup"><span data-stu-id="6a322-110">For Windows, this means the values are equivalent to what they were in .NET Framework and .NET Core 1.0 - 3.1.</span></span> <span data-ttu-id="6a322-111">Para Linux e macOS, os <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> valores agora correspondem aos <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> valores para o Windows.</span><span class="sxs-lookup"><span data-stu-id="6a322-111">For Linux and macOS, the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values now match the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for Windows.</span></span>

<span data-ttu-id="6a322-112">A tabela a seguir resume as alterações de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> valores.</span><span class="sxs-lookup"><span data-stu-id="6a322-112">The following table summarizes the changes for <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values.</span></span>

| | <span data-ttu-id="6a322-113">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a322-113">.NET Framework</span></span><br/><span data-ttu-id="6a322-114">.NET Core 1,0-3,1</span><span class="sxs-lookup"><span data-stu-id="6a322-114">.NET Core 1.0 - 3.1</span></span> | <span data-ttu-id="6a322-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="6a322-115">.NET 5.0</span></span> | <span data-ttu-id="6a322-116">.NET 5.0.1</span><span class="sxs-lookup"><span data-stu-id="6a322-116">.NET 5.0.1</span></span> |
-|-|-|-
| <span data-ttu-id="6a322-117">**Windows**</span><span class="sxs-lookup"><span data-stu-id="6a322-117">**Windows**</span></span> | <span data-ttu-id="6a322-118">Obter do NLS</span><span class="sxs-lookup"><span data-stu-id="6a322-118">Obtain from NLS</span></span> | <span data-ttu-id="6a322-119">Separador decimal do ICU.</span><span class="sxs-lookup"><span data-stu-id="6a322-119">Decimal separator from ICU.</span></span><br/><span data-ttu-id="6a322-120">Pode voltar para o NLS.</span><span class="sxs-lookup"><span data-stu-id="6a322-120">Can switch back to NLS.</span></span> | <span data-ttu-id="6a322-121">Equivalente ao NLS</span><span class="sxs-lookup"><span data-stu-id="6a322-121">Equivalent to NLS</span></span> |
| <span data-ttu-id="6a322-122">**Linux e macOS**</span><span class="sxs-lookup"><span data-stu-id="6a322-122">**Linux and macOS**</span></span> | <span data-ttu-id="6a322-123">Separador decimal do ICU</span><span class="sxs-lookup"><span data-stu-id="6a322-123">Decimal separator from ICU</span></span> | <span data-ttu-id="6a322-124">Separador decimal do ICU</span><span class="sxs-lookup"><span data-stu-id="6a322-124">Decimal separator from ICU</span></span> | <span data-ttu-id="6a322-125">Equivalente ao NLS</span><span class="sxs-lookup"><span data-stu-id="6a322-125">Equivalent to NLS</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="6a322-126">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="6a322-126">Version introduced</span></span>

<span data-ttu-id="6a322-127">5.0.1</span><span class="sxs-lookup"><span data-stu-id="6a322-127">5.0.1</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6a322-128">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="6a322-128">Reason for change</span></span>

<span data-ttu-id="6a322-129">Os desenvolvedores relataram que usam a <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> propriedade ao analisar arquivos de valores separados por vírgulas (CSV) e os novos valores desapareceram <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> que a análise.</span><span class="sxs-lookup"><span data-stu-id="6a322-129">Developers reported that they use the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> property when parsing comma-separated value (CSV) files, and the new <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values broke that parsing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6a322-130">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="6a322-130">Recommended action</span></span>

<span data-ttu-id="6a322-131">Se o seu código depende dos valores de separadores decimais anteriores, você pode codificar os valores desejados <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6a322-131">If your code relies on the previous decimal separator values, you can hardcode the desired <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6a322-132">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="6a322-132">Affected APIs</span></span>

- <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=fullName>

<!--

#### Category

- Globalization

### Affected APIs

- `P:System.Globalization.TextInfo.ListSeparator`

-->
