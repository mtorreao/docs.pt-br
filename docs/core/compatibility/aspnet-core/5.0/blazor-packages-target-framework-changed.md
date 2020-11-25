---
title: 'Alteração significativa: mais incrivelmente: estrutura de destino de pacotes NuGet alterada'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulados mais recentes: estrutura de destino de pacotes NuGet alterada'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 5515edc66ff9786f0d8f7e24e5fc28c71502567b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760378"
---
# <a name="blazor-target-framework-of-nuget-packages-changed"></a><span data-ttu-id="06ab9-103">Mais incrivelmente: estrutura de destino de pacotes NuGet alterada</span><span class="sxs-lookup"><span data-stu-id="06ab9-103">Blazor: Target framework of NuGet packages changed</span></span>

<span data-ttu-id="06ab9-104">Os projetos Webassembly mais po3,2 foram compilados para o destino .NET Standard 2,1 ( `<TargetFramework>netstandard2.1</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="06ab9-104">Blazor 3.2 WebAssembly projects were compiled to target .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span></span> <span data-ttu-id="06ab9-105">No ASP.NET Core 5,0, os 5,0 projetos de um servidor de Webassembly mais podriveres e mais de um e mais do mais `<TargetFramework>net5.0</TargetFramework>`</span><span class="sxs-lookup"><span data-stu-id="06ab9-105">In ASP.NET Core 5.0, both Blazor Server and Blazor WebAssembly projects target .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span></span> <span data-ttu-id="06ab9-106">Para alinhar melhor com a alteração da estrutura de destino, os seguintes pacotes mais eficientes não são mais direcionados .NET Standard 2,1:</span><span class="sxs-lookup"><span data-stu-id="06ab9-106">To better align with the target framework change, the following Blazor packages no longer target .NET Standard 2.1:</span></span>

* [<span data-ttu-id="06ab9-107">Microsoft. AspNetCore. Components</span><span class="sxs-lookup"><span data-stu-id="06ab9-107">Microsoft.AspNetCore.Components</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [<span data-ttu-id="06ab9-108">Microsoft. AspNetCore. Components. Authorization</span><span class="sxs-lookup"><span data-stu-id="06ab9-108">Microsoft.AspNetCore.Components.Authorization</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [<span data-ttu-id="06ab9-109">Microsoft. AspNetCore. Components. Forms</span><span class="sxs-lookup"><span data-stu-id="06ab9-109">Microsoft.AspNetCore.Components.Forms</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [<span data-ttu-id="06ab9-110">Microsoft. AspNetCore. Components. Web</span><span class="sxs-lookup"><span data-stu-id="06ab9-110">Microsoft.AspNetCore.Components.Web</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [<span data-ttu-id="06ab9-111">Microsoft. AspNetCore. Components. Webassembly</span><span class="sxs-lookup"><span data-stu-id="06ab9-111">Microsoft.AspNetCore.Components.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [<span data-ttu-id="06ab9-112">Microsoft. AspNetCore. Components. Webassembly. Authentication</span><span class="sxs-lookup"><span data-stu-id="06ab9-112">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [<span data-ttu-id="06ab9-113"> Interoperabilidade deMicrosoft.JS</span><span class="sxs-lookup"><span data-stu-id="06ab9-113">Microsoft.JSInterop</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop)
* [<span data-ttu-id="06ab9-114">Microsoft.JSInterop. Webassembly</span><span class="sxs-lookup"><span data-stu-id="06ab9-114">Microsoft.JSInterop.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [<span data-ttu-id="06ab9-115">Microsoft. Authentication. Webassembly. MSAL</span><span class="sxs-lookup"><span data-stu-id="06ab9-115">Microsoft.Authentication.WebAssembly.Msal</span></span>](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

<span data-ttu-id="06ab9-116">Para obter uma discussão, consulte o problema do GitHub [dotnet/aspnetcore # 23424](https://github.com/dotnet/aspnetcore/issues/23424).</span><span class="sxs-lookup"><span data-stu-id="06ab9-116">For discussion, see GitHub issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="06ab9-117">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="06ab9-117">Version introduced</span></span>

<span data-ttu-id="06ab9-118">5,0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="06ab9-118">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="06ab9-119">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="06ab9-119">Old behavior</span></span>

<span data-ttu-id="06ab9-120">No mais 3,1 e 3,2, os pacotes visam .NET Standard 2,1 e o .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="06ab9-120">In Blazor 3.1 and 3.2, packages target .NET Standard 2.1 and .NET Core 3.1.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="06ab9-121">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="06ab9-121">New behavior</span></span>

<span data-ttu-id="06ab9-122">No ASP.NET Core 5,0, os pacotes são de destino .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="06ab9-122">In ASP.NET Core 5.0, packages target .NET 5.0.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="06ab9-123">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="06ab9-123">Reason for change</span></span>

<span data-ttu-id="06ab9-124">A alteração foi feita para se alinhar melhor com os requisitos da estrutura de destino do .NET.</span><span class="sxs-lookup"><span data-stu-id="06ab9-124">The change was made to better align with .NET target framework requirements.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="06ab9-125">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="06ab9-125">Recommended action</span></span>

<span data-ttu-id="06ab9-126">Os projetos Webassembly mais po3,2 devem ter como destino o .NET 5,0 como parte da atualização de suas referências de pacote para 5. x.x.</span><span class="sxs-lookup"><span data-stu-id="06ab9-126">Blazor 3.2 WebAssembly projects should target .NET 5.0 as part of updating their package references to 5.x.x.</span></span> <span data-ttu-id="06ab9-127">As bibliotecas que fazem referência a um desses pacotes podem ter como destino o .NET 5,0 ou vários destinos, dependendo de seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="06ab9-127">Libraries that reference one of these packages can either target .NET 5.0 or multi-target depending on their requirements.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="06ab9-128">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="06ab9-128">Affected APIs</span></span>

<span data-ttu-id="06ab9-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="06ab9-129">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
