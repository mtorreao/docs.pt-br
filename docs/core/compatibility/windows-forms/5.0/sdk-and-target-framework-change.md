---
title: 'Alteração significativa: os aplicativos WinForms e WPF usam Microsoft. NET. Sdk'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que os aplicativos Windows Forms e Windows Presentation Framework agora usam o SDK do .NET em vez dos WinForms do .NET Core e do SDK do WPF.
ms.date: 09/18/2020
ms.openlocfilehash: 5f25be44c390abc173f155351d8cb007a6b370b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760478"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="2ff06-103">Os aplicativos WinForms e WPF usam Microsoft. NET. Sdk</span><span class="sxs-lookup"><span data-stu-id="2ff06-103">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="2ff06-104">Os aplicativos Windows Forms e Windows Presentation Framework (WPF) agora usam o SDK do .NET ( `Microsoft.NET.Sdk` ) em vez do .NET Core WinForms e do SDK do WPF ( `Microsoft.NET.Sdk.WindowsDesktop` ).</span><span class="sxs-lookup"><span data-stu-id="2ff06-104">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

## <a name="change-description"></a><span data-ttu-id="2ff06-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="2ff06-105">Change description</span></span>

<span data-ttu-id="2ff06-106">Nas versões anteriores do .NET Core, os aplicativos WinForms e WPF usavam um [SDK de projeto](../../../project-sdk/overview.md) separado ( `Microsoft.NET.Sdk.WindowsDesktop` ).</span><span class="sxs-lookup"><span data-stu-id="2ff06-106">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="2ff06-107">A partir do .NET 5,0, o SDK do WinForms e do WPF foi unificado com o SDK do .NET ( `Microsoft.NET.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="2ff06-107">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="2ff06-108">Além disso, novos [monikers do Framework de destino (TFM)](../../../../standard/frameworks.md) substituem `netcoreapp` e `netstandard` no .NET 5.</span><span class="sxs-lookup"><span data-stu-id="2ff06-108">In addition, new [target framework monikers (TFM)](../../../../standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="2ff06-109">O exemplo a seguir mostra as alterações que você precisaria fazer para um arquivo de projeto do WPF ao redirecionar para o .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="2ff06-109">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="2ff06-110">Nas versões anteriores do .NET Core:</span><span class="sxs-lookup"><span data-stu-id="2ff06-110">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="2ff06-111">No .NET 5,0 e versões posteriores:</span><span class="sxs-lookup"><span data-stu-id="2ff06-111">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a><span data-ttu-id="2ff06-112">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="2ff06-112">Version introduced</span></span>

<span data-ttu-id="2ff06-113">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="2ff06-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2ff06-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="2ff06-114">Recommended action</span></span>

<span data-ttu-id="2ff06-115">No seu arquivo de projeto do WPF ou Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="2ff06-115">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="2ff06-116">Atualize o `Sdk` atributo para `Microsoft.NET.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="2ff06-116">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="2ff06-117">Atualize a `TargetFramework` propriedade para `net5.0-windows` .</span><span class="sxs-lookup"><span data-stu-id="2ff06-117">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2ff06-118">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="2ff06-118">Affected APIs</span></span>

<span data-ttu-id="2ff06-119">Não detectável via análise de API.</span><span class="sxs-lookup"><span data-stu-id="2ff06-119">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
