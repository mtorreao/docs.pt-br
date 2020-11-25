---
title: 'Alteração significativa: APIs Pubternal removidas'
description: Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 em que algumas APIs de localização pubternal foram removidas
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: ae647d66b716175536edb3c978b027ebb7d3ddac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760341"
---
# <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="84d9c-103">Localização: APIs "Pubternal" removidas</span><span class="sxs-lookup"><span data-stu-id="84d9c-103">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="84d9c-104">Para manter melhor a superfície da API pública do ASP.NET Core, algumas :::no-loc text="\"pubternal\""::: APIs de localização foram removidas.</span><span class="sxs-lookup"><span data-stu-id="84d9c-104">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="84d9c-105">Uma :::no-loc text="\"pubternal\""::: API tem um `public` modificador de acesso e é definida em um namespace que implica uma intenção [interna](../../../../csharp/language-reference/keywords/internal.md) .</span><span class="sxs-lookup"><span data-stu-id="84d9c-105">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](../../../../csharp/language-reference/keywords/internal.md) intent.</span></span>

<span data-ttu-id="84d9c-106">Para obter uma discussão, consulte [dotnet/aspnetcore # 22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="84d9c-106">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="84d9c-107">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="84d9c-107">Version introduced</span></span>

<span data-ttu-id="84d9c-108">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="84d9c-108">5.0 Preview 6</span></span>

## <a name="old-behavior"></a><span data-ttu-id="84d9c-109">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="84d9c-109">Old behavior</span></span>

<span data-ttu-id="84d9c-110">As seguintes APIs foram `public` :</span><span class="sxs-lookup"><span data-stu-id="84d9c-110">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="84d9c-111">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` sobrecargas de Construtor aceitam qualquer um dos seguintes tipos de parâmetro:</span><span class="sxs-lookup"><span data-stu-id="84d9c-111">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

## <a name="new-behavior"></a><span data-ttu-id="84d9c-112">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="84d9c-112">New behavior</span></span>

<span data-ttu-id="84d9c-113">A lista a seguir descreve as alterações:</span><span class="sxs-lookup"><span data-stu-id="84d9c-113">The following list outlines the changes:</span></span>

- <span data-ttu-id="84d9c-114">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper``Microsoft.Extensions.Localization.AssemblyWrapper`já se tornou e agora é `internal` .</span><span class="sxs-lookup"><span data-stu-id="84d9c-114">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="84d9c-115">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider``Microsoft.Extensions.Localization.Internal.IResourceStringProvider`já se tornou e agora é `internal` .</span><span class="sxs-lookup"><span data-stu-id="84d9c-115">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="84d9c-116">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` as sobrecargas de construtor que aceitam qualquer um dos seguintes tipos de parâmetro agora são `internal` :</span><span class="sxs-lookup"><span data-stu-id="84d9c-116">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

## <a name="reason-for-change"></a><span data-ttu-id="84d9c-117">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="84d9c-117">Reason for change</span></span>

<span data-ttu-id="84d9c-118">Explicado mais detalhadamente em [ASPNET/comunicados # 377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), os :::no-loc text="\"pubternal\""::: tipos foram removidos da `public` superfície da API.</span><span class="sxs-lookup"><span data-stu-id="84d9c-118">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="84d9c-119">Essas alterações se adaptam a mais classes para essa decisão de design.</span><span class="sxs-lookup"><span data-stu-id="84d9c-119">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="84d9c-120">As classes em questão eram pretendidas como pontos de extensão para os testes internos da equipe.</span><span class="sxs-lookup"><span data-stu-id="84d9c-120">The classes in question were intended as extension points for the team's internal testing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="84d9c-121">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="84d9c-121">Recommended action</span></span>

<span data-ttu-id="84d9c-122">Embora seja improvável, alguns aplicativos podem depender intencionalmente ou acidentalmente, dependendo dos :::no-loc text="\"pubternal\""::: tipos.</span><span class="sxs-lookup"><span data-stu-id="84d9c-122">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="84d9c-123">Consulte as [novas](#new-behavior) seções de comportamento para determinar como migrar para fora dos tipos.</span><span class="sxs-lookup"><span data-stu-id="84d9c-123">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="84d9c-124">Se você identificou um cenário que a API pública permitiu antes dessa alteração, mas não agora, execute um problema em [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="84d9c-124">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="84d9c-125">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="84d9c-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
