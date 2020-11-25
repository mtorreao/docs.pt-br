---
title: 'Alteração significativa: HTTP: Kestrel e tipos BadHttpRequestException do IIS marcados como obsoletos e substituídos'
description: 'Saiba mais sobre a alteração significativa em ASP.NET Core 5,0 intitulado HTTP: Kestrel e tipos BadHttpRequestException do IIS marcados como obsoletos e substituídos'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c51b1dd9d708c04bc1bbcfb65ea2e9daea5330b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760374"
---
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="105a2-103">Tipos de BadHttpRequestException de HTTP: Kestrel e IIS marcados como obsoletos e substituídos</span><span class="sxs-lookup"><span data-stu-id="105a2-103">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="105a2-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` foram marcados como obsoletos e alterados para derivar de `Microsoft.AspNetCore.Http.BadHttpRequestException` .</span><span class="sxs-lookup"><span data-stu-id="105a2-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="105a2-105">Os servidores Kestrel e IIS ainda lançam seus tipos de exceção antigos para compatibilidade com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="105a2-105">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="105a2-106">Os tipos obsoletos serão removidos em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="105a2-106">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="105a2-107">Para obter uma discussão, consulte [dotnet/aspnetcore # 20614](https://github.com/dotnet/aspnetcore/issues/20614).</span><span class="sxs-lookup"><span data-stu-id="105a2-107">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="105a2-108">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="105a2-108">Version introduced</span></span>

<span data-ttu-id="105a2-109">5,0 versão prévia 4</span><span class="sxs-lookup"><span data-stu-id="105a2-109">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="105a2-110">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="105a2-110">Old behavior</span></span>

<span data-ttu-id="105a2-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derivado de <xref:System.IO.IOException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="105a2-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="105a2-112">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="105a2-112">New behavior</span></span>

<span data-ttu-id="105a2-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` são obsoletos.</span><span class="sxs-lookup"><span data-stu-id="105a2-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="105a2-114">Os tipos também derivam de `Microsoft.AspNetCore.Http.BadHttpRequestException` , que deriva de `System.IO.IOException` .</span><span class="sxs-lookup"><span data-stu-id="105a2-114">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="105a2-115">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="105a2-115">Reason for change</span></span>

<span data-ttu-id="105a2-116">A alteração foi feita em:</span><span class="sxs-lookup"><span data-stu-id="105a2-116">The change was made to:</span></span>

* <span data-ttu-id="105a2-117">Consolide tipos duplicados.</span><span class="sxs-lookup"><span data-stu-id="105a2-117">Consolidate duplicate types.</span></span>
* <span data-ttu-id="105a2-118">Unificar o comportamento entre implementações do servidor.</span><span class="sxs-lookup"><span data-stu-id="105a2-118">Unify behavior across server implementations.</span></span>

<span data-ttu-id="105a2-119">Um aplicativo agora pode capturar a exceção base `Microsoft.AspNetCore.Http.BadHttpRequestException` ao usar o Kestrel ou o IIS.</span><span class="sxs-lookup"><span data-stu-id="105a2-119">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="105a2-120">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="105a2-120">Recommended action</span></span>

<span data-ttu-id="105a2-121">Substitua os usos de `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` por `Microsoft.AspNetCore.Http.BadHttpRequestException` .</span><span class="sxs-lookup"><span data-stu-id="105a2-121">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="105a2-122">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="105a2-122">Affected APIs</span></span>

- [<span data-ttu-id="105a2-123">Microsoft. AspNetCore. Server. IIS. BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="105a2-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="105a2-124">Microsoft. AspNetCore. Server. Kestrel. BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="105a2-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
