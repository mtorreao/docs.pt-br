---
title: 'Alteração significativa: mais grande: o recurso ProtectedBrowserStorage mudou para a estrutura compartilhada'
description: 'Saiba mais sobre as alterações significativas no ASP.NET Core 5,0 intitulados mais recentes: o recurso ProtectedBrowserStorage mudou para a estrutura compartilhada'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c8058adf8b66aef8dd011ea672cd306ae4de60a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760377"
---
# <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="6ca06-103">Mais incrivelmente: o recurso ProtectedBrowserStorage mudou para a estrutura compartilhada</span><span class="sxs-lookup"><span data-stu-id="6ca06-103">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="6ca06-104">Como parte da versão do ASP.NET Core RC2 5,0, o `ProtectedBrowserStorage` recurso foi movido para a estrutura compartilhada ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6ca06-104">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6ca06-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="6ca06-105">Version introduced</span></span>

<span data-ttu-id="6ca06-106">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="6ca06-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6ca06-107">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="6ca06-107">Old behavior</span></span>

<span data-ttu-id="6ca06-108">No ASP.NET Core 5,0 Preview 8, o recurso está disponível como parte do pacote [Microsoft. AspNetCore. Components. Web. Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) , mas só pode ser usado no Webassembly de mais incrivelmente.</span><span class="sxs-lookup"><span data-stu-id="6ca06-108">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="6ca06-109">No ASP.NET Core 5,0 RC1, o recurso está disponível como parte do pacote [Microsoft. AspNetCore. Components. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) , que faz referência à `Microsoft.AspNetCore.App` estrutura compartilhada.</span><span class="sxs-lookup"><span data-stu-id="6ca06-109">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="6ca06-110">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="6ca06-110">New behavior</span></span>

<span data-ttu-id="6ca06-111">No ASP.NET Core 5,0 RC2, uma referência de pacote NuGet não é mais necessária para referenciar e usar o recurso.</span><span class="sxs-lookup"><span data-stu-id="6ca06-111">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6ca06-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="6ca06-112">Reason for change</span></span>

<span data-ttu-id="6ca06-113">A mudança para a estrutura compartilhada é uma melhor opção para a experiência do usuário que os clientes esperam.</span><span class="sxs-lookup"><span data-stu-id="6ca06-113">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6ca06-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="6ca06-114">Recommended action</span></span>

<span data-ttu-id="6ca06-115">Se estiver atualizando do ASP.NET Core 5,0 RC1, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6ca06-115">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="6ca06-116">Remova a `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` referência do pacote do projeto.</span><span class="sxs-lookup"><span data-stu-id="6ca06-116">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="6ca06-117">Substitua `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` por `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="6ca06-117">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="6ca06-118">Remova a chamada de `AddProtectedBrowserStorage` de sua `Startup` classe.</span><span class="sxs-lookup"><span data-stu-id="6ca06-118">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="6ca06-119">Se estiver atualizando do ASP.NET Core 5,0 Preview 8, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6ca06-119">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="6ca06-120">Remova a `Microsoft.AspNetCore.Components.Web.Extensions` referência do pacote do projeto.</span><span class="sxs-lookup"><span data-stu-id="6ca06-120">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="6ca06-121">Substitua `using Microsoft.AspNetCore.Components.Web.Extensions;` por `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span><span class="sxs-lookup"><span data-stu-id="6ca06-121">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="6ca06-122">Remova a chamada de `AddProtectedBrowserStorage` de sua `Startup` classe.</span><span class="sxs-lookup"><span data-stu-id="6ca06-122">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6ca06-123">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="6ca06-123">Affected APIs</span></span>

<span data-ttu-id="6ca06-124">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6ca06-124">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
