---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032252"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="1839f-101">Kestrel: abstrações de transporte removidas e tornadas públicas</span><span class="sxs-lookup"><span data-stu-id="1839f-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="1839f-102">Como parte da afastamento das APIs "pubternal", as APIs da camada de transporte do Kestrel são expostas como uma interface pública na `Microsoft.AspNetCore.Connections.Abstractions` biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1839f-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1839f-103">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="1839f-103">Version introduced</span></span>

<span data-ttu-id="1839f-104">3.0</span><span class="sxs-lookup"><span data-stu-id="1839f-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1839f-105">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="1839f-105">Old behavior</span></span>

- <span data-ttu-id="1839f-106">Abstrações relacionadas ao transporte estavam disponíveis na `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1839f-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="1839f-107">A `ListenOptions.NoDelay` Propriedade estava disponível.</span><span class="sxs-lookup"><span data-stu-id="1839f-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1839f-108">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="1839f-108">New behavior</span></span>

- <span data-ttu-id="1839f-109">A `IConnectionListener` interface foi introduzida na `Microsoft.AspNetCore.Connections.Abstractions` biblioteca para expor a funcionalidade mais usada da `...Transport.Abstractions` biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1839f-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="1839f-110">O `NoDelay` agora está disponível em opções de transporte ( `LibuvTransportOptions` e `SocketTransportOptions` ).</span><span class="sxs-lookup"><span data-stu-id="1839f-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="1839f-111">`SchedulingMode` Não está mais disponível.</span><span class="sxs-lookup"><span data-stu-id="1839f-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1839f-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="1839f-112">Reason for change</span></span>

<span data-ttu-id="1839f-113">ASP.NET Core 3,0 foi afastado das APIs "pubternal".</span><span class="sxs-lookup"><span data-stu-id="1839f-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1839f-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="1839f-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="1839f-115">Categoria</span><span class="sxs-lookup"><span data-stu-id="1839f-115">Category</span></span>

<span data-ttu-id="1839f-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1839f-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1839f-117">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="1839f-117">Affected APIs</span></span>

<span data-ttu-id="1839f-118">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1839f-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
