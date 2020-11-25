---
title: 'Alteração significativa: ordem das marcas na atividade. as marcas são revertidas'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que Activity. Tags agora armazena itens na lista de acordo com a ordem em que são adicionados.
ms.date: 11/01/2020
ms.openlocfilehash: 1ff14dc1a4f7a0bf8cf9e79f3750b819f4d4a5ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760386"
---
# <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="e822c-103">Ordem das marcas na atividade. as marcas são revertidas</span><span class="sxs-lookup"><span data-stu-id="e822c-103">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="e822c-104"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> Agora armazena itens na lista de acordo com a ordem em que são adicionados, ou seja, o primeiro item que é adicionado é o primeiro na lista.</span><span class="sxs-lookup"><span data-stu-id="e822c-104"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="e822c-105">Essa alteração foi feita para corresponder à [especificação de atributos OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span><span class="sxs-lookup"><span data-stu-id="e822c-105">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

## <a name="change-description"></a><span data-ttu-id="e822c-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="e822c-106">Change description</span></span>

<span data-ttu-id="e822c-107">Nas versões anteriores do .NET, o <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> armazena itens na ordem inversa da qual eles são adicionados.</span><span class="sxs-lookup"><span data-stu-id="e822c-107">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="e822c-108">Ou seja, o primeiro item adicionado é o último na lista.</span><span class="sxs-lookup"><span data-stu-id="e822c-108">That is, the first item added is last in the list.</span></span> <span data-ttu-id="e822c-109">A partir do .NET 5,0, a ordem dos itens é revertida e o primeiro item adicionado sempre é o primeiro na lista.</span><span class="sxs-lookup"><span data-stu-id="e822c-109">Starting in .NET 5.0, the order of the items is reversed, and the first item added is always first in the list.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e822c-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="e822c-110">Version introduced</span></span>

<span data-ttu-id="e822c-111">5.0</span><span class="sxs-lookup"><span data-stu-id="e822c-111">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e822c-112">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="e822c-112">Recommended action</span></span>

<span data-ttu-id="e822c-113">Se seu aplicativo tiver uma dependência na <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> ordem da lista e você estiver atualizando para o .net 5,0 ou posterior, você precisará alterar esta parte do seu código.</span><span class="sxs-lookup"><span data-stu-id="e822c-113">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5.0 or later, you'll need to change this part of your code.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e822c-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="e822c-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
