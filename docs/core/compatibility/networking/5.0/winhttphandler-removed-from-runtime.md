---
title: 'Alteração significativa: WinHttpHandler removido do tempo de execução do .NET'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que o WinHttpHandler foi removido do tempo de execução do .NET.
ms.date: 10/18/2020
ms.openlocfilehash: f8b9910ade8d459133791a23704d624a91cc5dff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760355"
---
# <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="1edd9-103">WinHttpHandler removido do tempo de execução do .NET</span><span class="sxs-lookup"><span data-stu-id="1edd9-103">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="1edd9-104">A `WinHttpHandler` classe foi removida do assembly *System.Net.Http.dll* .</span><span class="sxs-lookup"><span data-stu-id="1edd9-104">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="1edd9-105">Agora, ele está disponível apenas como um [pacote NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)fora de banda (OOB).</span><span class="sxs-lookup"><span data-stu-id="1edd9-105">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="1edd9-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="1edd9-106">Version introduced</span></span>

<span data-ttu-id="1edd9-107">5.0</span><span class="sxs-lookup"><span data-stu-id="1edd9-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="1edd9-108">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="1edd9-108">Change description</span></span>

<span data-ttu-id="1edd9-109">Nas versões anteriores do .NET, a <xref:System.Net.Http.WinHttpHandler> classe está disponível como parte das principais bibliotecas do .net.</span><span class="sxs-lookup"><span data-stu-id="1edd9-109">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="1edd9-110">A partir do .NET 5,0, a <xref:System.Net.Http.WinHttpHandler> classe só está disponível como um [pacote NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)instalado separadamente.</span><span class="sxs-lookup"><span data-stu-id="1edd9-110">Starting in .NET 5.0, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="1edd9-111">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="1edd9-111">Recommended action</span></span>

<span data-ttu-id="1edd9-112">Instale o [pacote NuGet System .net. http. WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="1edd9-112">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="1edd9-113">Ou, se você não precisar de recursos específicos do WinHTTP, use <xref:System.Net.Http.SocketsHttpHandler> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="1edd9-113">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="1edd9-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="1edd9-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
