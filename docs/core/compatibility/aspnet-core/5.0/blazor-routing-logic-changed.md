---
title: 'Alteração significativa: mais incrivelmente: alterações na lógica de roteamento em aplicativos mais Incrivelmenteos'
description: 'Saiba mais sobre as alterações significativas no ASP.NET Core 5,0 intitulados mais recentes: alterações na lógica de roteamento em aplicativos mais Incrivelmenteos'
author: scottaddie
ms.author: scaddie
ms.date: 12/14/2020
ms.openlocfilehash: 4ab8289565c88b17eb204a11724bb12a09b033c2
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513516"
---
# <a name="blazor-route-precedence-logic-changed-in-blazor-apps"></a><span data-ttu-id="ee00a-103">Mais incrivelmente: lógica de precedência de rota alterada em aplicativos mais Incrivelmenteos</span><span class="sxs-lookup"><span data-stu-id="ee00a-103">Blazor: Route precedence logic changed in Blazor apps</span></span>

<span data-ttu-id="ee00a-104">Um bug na implementação de roteamento mais incrivelmente afetou a forma como a precedência das rotas foi determinada.</span><span class="sxs-lookup"><span data-stu-id="ee00a-104">A bug in the Blazor routing implementation affected how the precedence of routes was determined.</span></span> <span data-ttu-id="ee00a-105">Esse bug afeta todas as rotas ou rotas com parâmetros opcionais em seu aplicativo mais rápido.</span><span class="sxs-lookup"><span data-stu-id="ee00a-105">This bug affects catch-all routes or routes with optional parameters within your Blazor app.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ee00a-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="ee00a-106">Version introduced</span></span>

<span data-ttu-id="ee00a-107">5.0.1</span><span class="sxs-lookup"><span data-stu-id="ee00a-107">5.0.1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ee00a-108">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="ee00a-108">Old behavior</span></span>

<span data-ttu-id="ee00a-109">Com o comportamento errado, as rotas com precedência mais baixa são consideradas e correspondidas em rotas com precedência mais alta.</span><span class="sxs-lookup"><span data-stu-id="ee00a-109">With the erroneous behavior, routes with lower precedence are considered and matched over routes with higher precedence.</span></span> <span data-ttu-id="ee00a-110">Por exemplo, a `{*slug}` rota é correspondida antes de `/customer/{id}` .</span><span class="sxs-lookup"><span data-stu-id="ee00a-110">For example, the `{*slug}` route is matched before `/customer/{id}`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="ee00a-111">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="ee00a-111">New behavior</span></span>

<span data-ttu-id="ee00a-112">O comportamento atual corresponde mais próximo ao comportamento de roteamento definido em aplicativos ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee00a-112">The current behavior more closely matches the routing behavior defined in ASP.NET Core apps.</span></span> <span data-ttu-id="ee00a-113">A estrutura determina primeiro a precedência de rota para cada segmento.</span><span class="sxs-lookup"><span data-stu-id="ee00a-113">The framework determines the route precedence for each segment first.</span></span> <span data-ttu-id="ee00a-114">O comprimento da rota é usado apenas como um segundo critério para quebrar as ligações.</span><span class="sxs-lookup"><span data-stu-id="ee00a-114">The route's length is used only as a second criteria to break ties.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ee00a-115">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="ee00a-115">Reason for change</span></span>

<span data-ttu-id="ee00a-116">O comportamento original é considerado um bug na implementação.</span><span class="sxs-lookup"><span data-stu-id="ee00a-116">The original behavior is considered a bug in the implementation.</span></span> <span data-ttu-id="ee00a-117">Como meta, o sistema de roteamento em aplicativos mais podestas deve se comportar da mesma forma que o sistema de roteamento no restante de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee00a-117">As a goal, the routing system in Blazor apps should behave the same way as the routing system in the rest of ASP.NET Core.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ee00a-118">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="ee00a-118">Recommended action</span></span>

<span data-ttu-id="ee00a-119">Se estiver atualizando de versões anteriores do mais do que o 5. x, use o `PreferExactMatches` atributo no `Router` componente.</span><span class="sxs-lookup"><span data-stu-id="ee00a-119">If upgrading from previous versions of Blazor to 5.x, use the `PreferExactMatches` attribute on the `Router` component.</span></span> <span data-ttu-id="ee00a-120">Esse atributo pode ser usado para aceitar o comportamento correto.</span><span class="sxs-lookup"><span data-stu-id="ee00a-120">This attribute can be used to opt into the correct behavior.</span></span> <span data-ttu-id="ee00a-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ee00a-121">For example:</span></span>

```razor
<Router AppAssembly="@typeof(Program).Assembly" PreferExactMatches="true">
```

<span data-ttu-id="ee00a-122">Quando `PreferExactMatches` é definido como `true` , a correspondência de rota prefere correspondências exatas sobre curingas.</span><span class="sxs-lookup"><span data-stu-id="ee00a-122">When `PreferExactMatches` is set to `true`, route matching prefers exact matches over wildcards.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ee00a-123">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="ee00a-123">Affected APIs</span></span>

<span data-ttu-id="ee00a-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ee00a-124">None</span></span>

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->
