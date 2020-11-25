---
title: 'Alteração significativa: autorização: o recurso no roteamento de ponto de extremidade é HttpContext'
description: 'Saiba mais sobre a alteração significativa na 5,0 ASP.NET Core a autorização intitulada: o recurso no roteamento do ponto de extremidade é HttpContext'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 7c5a77cb8999c60a7780b9b4f7ad2a1c79fd8310
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760524"
---
# <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="c226f-103">Autorização: o recurso no roteamento de ponto de extremidade é HttpContext</span><span class="sxs-lookup"><span data-stu-id="c226f-103">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="c226f-104">Ao usar o roteamento de ponto de extremidade no ASP.NET Core 3,1, o recurso usado para autorização é o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c226f-104">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="c226f-105">Essa abordagem não era suficiente para obter acesso aos dados da rota ( <xref:Microsoft.AspNetCore.Routing.RouteData> ).</span><span class="sxs-lookup"><span data-stu-id="c226f-105">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="c226f-106">Anteriormente no MVC, um <xref:Microsoft.AspNetCore.Http.HttpContext> recurso foi passado, o que permite o acesso ao ponto de extremidade ( <xref:Microsoft.AspNetCore.Http.Endpoint> ) e aos dados de rota.</span><span class="sxs-lookup"><span data-stu-id="c226f-106">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="c226f-107">Essa alteração garante que o recurso passado para autorização seja sempre o `HttpContext` .</span><span class="sxs-lookup"><span data-stu-id="c226f-107">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c226f-108">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="c226f-108">Version introduced</span></span>

<span data-ttu-id="c226f-109">5,0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="c226f-109">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="c226f-110">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="c226f-110">Old behavior</span></span>

<span data-ttu-id="c226f-111">Ao usar o roteamento de ponto de extremidade e os atributos de middleware de autorização ( <xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware> ) ou [[autorizar]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) , o recurso passado para autorização é o ponto de extremidade correspondente.</span><span class="sxs-lookup"><span data-stu-id="c226f-111">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="c226f-112">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="c226f-112">New behavior</span></span>

<span data-ttu-id="c226f-113">O roteamento do ponto de extremidade passa a `HttpContext` para a autorização.</span><span class="sxs-lookup"><span data-stu-id="c226f-113">Endpoint routing passes the `HttpContext` to authorization.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c226f-114">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="c226f-114">Reason for change</span></span>

<span data-ttu-id="c226f-115">Você pode acessar o ponto de extremidade do `HttpContext` .</span><span class="sxs-lookup"><span data-stu-id="c226f-115">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="c226f-116">No entanto, não havia como ir do ponto de extremidade para coisas como os dados de rota.</span><span class="sxs-lookup"><span data-stu-id="c226f-116">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="c226f-117">Houve uma perda na funcionalidade do roteamento sem ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c226f-117">There was a loss in functionality from non-endpoint routing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c226f-118">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="c226f-118">Recommended action</span></span>

<span data-ttu-id="c226f-119">Se seu aplicativo usar o recurso de ponto de extremidade, chame <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> no `HttpContext` para continuar acessando o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c226f-119">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="c226f-120">No ASP.NET Core 5,0 Preview 8 e posterior, você pode reverter para o comportamento antigo com o <xref:System.AppContext.SetSwitch%2A> .</span><span class="sxs-lookup"><span data-stu-id="c226f-120">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="c226f-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c226f-121">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

## <a name="affected-apis"></a><span data-ttu-id="c226f-122">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="c226f-122">Affected APIs</span></span>

<span data-ttu-id="c226f-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c226f-123">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
