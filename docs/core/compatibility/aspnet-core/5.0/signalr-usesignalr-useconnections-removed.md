---
title: 'Alteração significativa: Signalr: UseSignalR e métodos UseConnections removidos'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core o Signaler intitulada 5,0: métodos UseSignalR e UseConnections removidos'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1b1fce04518e69927cdc1650cc1e19107cc81e3b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760340"
---
# <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="ead6e-103">Signalr: métodos UseSignalR e UseConnections removidos</span><span class="sxs-lookup"><span data-stu-id="ead6e-103">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="ead6e-104">No ASP.NET Core 3,0, o Signalr adotou o roteamento de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ead6e-104">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="ead6e-105">Como parte dessa alteração, o <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A> , <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> e alguns métodos relacionados foram marcados como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="ead6e-105">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="ead6e-106">No ASP.NET Core 5,0, esses métodos obsoletos foram removidos.</span><span class="sxs-lookup"><span data-stu-id="ead6e-106">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="ead6e-107">Para obter a lista completa de métodos, consulte [APIs afetadas](#affected-apis).</span><span class="sxs-lookup"><span data-stu-id="ead6e-107">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="ead6e-108">Para obter uma discussão sobre esse problema, consulte [dotnet/aspnetcore # 20082](https://github.com/dotnet/aspnetcore/issues/20082).</span><span class="sxs-lookup"><span data-stu-id="ead6e-108">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ead6e-109">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="ead6e-109">Version introduced</span></span>

<span data-ttu-id="ead6e-110">5,0 Preview 3</span><span class="sxs-lookup"><span data-stu-id="ead6e-110">5.0 Preview 3</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ead6e-111">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="ead6e-111">Old behavior</span></span>

<span data-ttu-id="ead6e-112">Os hubs de sinalização e os manipuladores de conexão podem ser registrados no pipeline de middleware usando os `UseSignalR` `UseConnections` métodos ou.</span><span class="sxs-lookup"><span data-stu-id="ead6e-112">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="ead6e-113">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="ead6e-113">New behavior</span></span>

<span data-ttu-id="ead6e-114">Os hubs de sinalização e os manipuladores de conexão devem ser registrados no <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> usando os <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> métodos de extensão e no <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder> .</span><span class="sxs-lookup"><span data-stu-id="ead6e-114">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ead6e-115">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="ead6e-115">Reason for change</span></span>

<span data-ttu-id="ead6e-116">Os métodos antigos tinham lógica de roteamento personalizada que não interagia com outros componentes de roteamento em ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ead6e-116">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="ead6e-117">No ASP.NET Core 3,0, um novo sistema de roteamento de uso geral, chamado de roteamento de ponto de extremidade, foi introduzido.</span><span class="sxs-lookup"><span data-stu-id="ead6e-117">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="ead6e-118">O Signalr habilitado para roteamento de ponto de extremidade para interagir com outros componentes de roteamento.</span><span class="sxs-lookup"><span data-stu-id="ead6e-118">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="ead6e-119">Alternar para esse modelo permite que os usuários percebam os benefícios completos do roteamento do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ead6e-119">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="ead6e-120">Consequentemente, os métodos antigos foram removidos.</span><span class="sxs-lookup"><span data-stu-id="ead6e-120">Consequently, the old methods have been removed.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ead6e-121">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="ead6e-121">Recommended action</span></span>

<span data-ttu-id="ead6e-122">Remova o código que chama `UseSignalR` ou `UseConnections` do método do projeto `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="ead6e-122">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="ead6e-123">Substitua-o por chamadas para `MapHub` ou `MapConnectionHandler` , respectivamente, no corpo de uma chamada para `UseEndpoints` .</span><span class="sxs-lookup"><span data-stu-id="ead6e-123">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="ead6e-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ead6e-124">For example:</span></span>

<span data-ttu-id="ead6e-125">**Código antigo:**</span><span class="sxs-lookup"><span data-stu-id="ead6e-125">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="ead6e-126">**Novo código:**</span><span class="sxs-lookup"><span data-stu-id="ead6e-126">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="ead6e-127">Em geral, suas `MapHub` chamadas e anteriores `MapConnectionHandler` podem ser transferidas diretamente do corpo de `UseSignalR` e `UseConnections` para `UseEndpoints` com pouca ou nenhuma alteração necessária.</span><span class="sxs-lookup"><span data-stu-id="ead6e-127">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ead6e-128">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="ead6e-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
