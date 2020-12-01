---
title: 'Alteração significativa: Localização: classe ResourceManagerWithCultureStringLocalizer e membro de interface WithCulture removido'
description: 'Saiba mais sobre a alteração significativa na ASP.NET Core 5,0 localização de título: classe ResourceManagerWithCultureStringLocalizer e membro da interface WithCulture removidos'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: ac7723cd9b961b34b3f87a55119d421668c87417
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437854"
---
# <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a><span data-ttu-id="4710f-103">Localização: classe ResourceManagerWithCultureStringLocalizer e membro da interface WithCulture removidos</span><span class="sxs-lookup"><span data-stu-id="4710f-103">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>

<span data-ttu-id="4710f-104">A classe [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) e o método [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) foram removidos no .NET 5,0 Preview 1.</span><span class="sxs-lookup"><span data-stu-id="4710f-104">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were removed in .NET 5.0 Preview 1.</span></span>

<span data-ttu-id="4710f-105">Para contexto, consulte [ASPNET/comunicados # 346](https://github.com/aspnet/Announcements/issues/346) e [dotnet/aspnetcore # 3324](https://github.com/dotnet/aspnetcore/issues/3324).</span><span class="sxs-lookup"><span data-stu-id="4710f-105">For context, see [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) and [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324).</span></span> <span data-ttu-id="4710f-106">Para discussão sobre essa alteração, consulte [dotnet/aspnetcore # 7756](https://github.com/dotnet/aspnetcore/issues/7756).</span><span class="sxs-lookup"><span data-stu-id="4710f-106">For discussion on this change, see [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4710f-107">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="4710f-107">Version introduced</span></span>

<span data-ttu-id="4710f-108">5,0 visualização 1</span><span class="sxs-lookup"><span data-stu-id="4710f-108">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="4710f-109">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="4710f-109">Old behavior</span></span>

<span data-ttu-id="4710f-110">A `ResourceManagerWithCultureStringLocalizer` classe e o `ResourceManagerStringLocalizer.WithCulture` método são [obsoletos no .NET Core 3,0 Preview 3 e posterior](../../3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span><span class="sxs-lookup"><span data-stu-id="4710f-110">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method are [obsolete in .NET Core 3.0 Preview 3 and later](../../3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).</span></span>

## <a name="new-behavior"></a><span data-ttu-id="4710f-111">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="4710f-111">New behavior</span></span>

<span data-ttu-id="4710f-112">A `ResourceManagerWithCultureStringLocalizer` classe e o `ResourceManagerStringLocalizer.WithCulture` método foram removidos no .NET 5,0 Preview 1.</span><span class="sxs-lookup"><span data-stu-id="4710f-112">The `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method have been removed in .NET 5.0 Preview 1.</span></span> <span data-ttu-id="4710f-113">Para obter um inventário das alterações feitas, consulte a solicitação pull em [dotnet/Extensions # 2562](https://github.com/dotnet/extensions/pull/2562/files).</span><span class="sxs-lookup"><span data-stu-id="4710f-113">For an inventory of the changes made, see the pull request at [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4710f-114">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="4710f-114">Reason for change</span></span>

<span data-ttu-id="4710f-115">A classe [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) e o método [ResourceManagerStringLocalizer. WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) geralmente eram fontes de confusão para os usuários da localização.</span><span class="sxs-lookup"><span data-stu-id="4710f-115">The [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) class and [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) method were often sources of confusion for users of localization.</span></span> <span data-ttu-id="4710f-116">A confusão era especialmente alta ao criar uma <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementação personalizada.</span><span class="sxs-lookup"><span data-stu-id="4710f-116">The confusion was especially high when creating a custom <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementation.</span></span> <span data-ttu-id="4710f-117">Essa classe e o método dão aos consumidores a impressão de que uma `IStringLocalizer` instância deve ser "por idioma, por recurso".</span><span class="sxs-lookup"><span data-stu-id="4710f-117">This class and method give consumers the impression that an `IStringLocalizer` instance is expected to be "per-language, per-resource".</span></span> <span data-ttu-id="4710f-118">Na realidade, a instância só deve ser "por recurso".</span><span class="sxs-lookup"><span data-stu-id="4710f-118">In reality, the instance should only be "per-resource".</span></span> <span data-ttu-id="4710f-119">Em tempo de execução, a <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> propriedade determina o idioma a ser usado.</span><span class="sxs-lookup"><span data-stu-id="4710f-119">At run time, the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> property determines the language to be used.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4710f-120">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="4710f-120">Recommended action</span></span>

<span data-ttu-id="4710f-121">Pare de usar a `ResourceManagerWithCultureStringLocalizer` classe e o `ResourceManagerStringLocalizer.WithCulture` método.</span><span class="sxs-lookup"><span data-stu-id="4710f-121">Stop using the `ResourceManagerWithCultureStringLocalizer` class and the `ResourceManagerStringLocalizer.WithCulture` method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4710f-122">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="4710f-122">Affected APIs</span></span>

- [<span data-ttu-id="4710f-123">ResourceManagerWithCultureStringLocalizer</span><span class="sxs-lookup"><span data-stu-id="4710f-123">ResourceManagerWithCultureStringLocalizer</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [<span data-ttu-id="4710f-124">ResourceManagerStringLocalizer.WithCulture</span><span class="sxs-lookup"><span data-stu-id="4710f-124">ResourceManagerStringLocalizer.WithCulture</span></span>](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
