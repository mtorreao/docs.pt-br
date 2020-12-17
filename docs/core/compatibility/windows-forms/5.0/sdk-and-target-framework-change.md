---
title: 'Alteração significativa: os aplicativos WinForms e WPF usam Microsoft. NET. Sdk'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que os aplicativos Windows Forms e Windows Presentation Framework agora usam o SDK do .NET em vez dos WinForms do .NET Core e do SDK do WPF.
ms.date: 09/18/2020
ms.openlocfilehash: 5eafed03fbf034f6a6457217a8527a877214e239
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633813"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="37402-103">Os aplicativos WinForms e WPF usam Microsoft. NET. Sdk</span><span class="sxs-lookup"><span data-stu-id="37402-103">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="37402-104">Os aplicativos Windows Forms e Windows Presentation Framework (WPF) agora usam o SDK do .NET ( `Microsoft.NET.Sdk` ) em vez do .NET Core WinForms e do SDK do WPF ( `Microsoft.NET.Sdk.WindowsDesktop` ).</span><span class="sxs-lookup"><span data-stu-id="37402-104">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

## <a name="change-description"></a><span data-ttu-id="37402-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="37402-105">Change description</span></span>

<span data-ttu-id="37402-106">Nas versões anteriores do .NET Core, os aplicativos WinForms e WPF usavam um [SDK de projeto](../../../project-sdk/overview.md) separado ( `Microsoft.NET.Sdk.WindowsDesktop` ).</span><span class="sxs-lookup"><span data-stu-id="37402-106">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="37402-107">A partir do .NET 5,0, o SDK do WinForms e do WPF foi unificado com o SDK do .NET ( `Microsoft.NET.Sdk` ).</span><span class="sxs-lookup"><span data-stu-id="37402-107">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="37402-108">Além disso, novos [monikers do Framework de destino (TFM)](../../../../standard/frameworks.md) substituem `netcoreapp` e `netstandard` no .NET 5.</span><span class="sxs-lookup"><span data-stu-id="37402-108">In addition, new [target framework monikers (TFM)](../../../../standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="37402-109">O exemplo a seguir mostra as alterações que você precisaria fazer para um arquivo de projeto do WPF ao redirecionar para o .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="37402-109">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="37402-110">Nas versões anteriores do .NET Core:</span><span class="sxs-lookup"><span data-stu-id="37402-110">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="37402-111">No .NET 5,0 e versões posteriores:</span><span class="sxs-lookup"><span data-stu-id="37402-111">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a><span data-ttu-id="37402-112">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="37402-112">Version introduced</span></span>

<span data-ttu-id="37402-113">SDK DO .NET 5.0.100</span><span class="sxs-lookup"><span data-stu-id="37402-113">.NET SDK 5.0.100</span></span>

## <a name="recommended-action"></a><span data-ttu-id="37402-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="37402-114">Recommended action</span></span>

<span data-ttu-id="37402-115">No seu arquivo de projeto do WPF ou Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="37402-115">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="37402-116">Atualize o `Sdk` atributo para `Microsoft.NET.Sdk` .</span><span class="sxs-lookup"><span data-stu-id="37402-116">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="37402-117">Atualize a `TargetFramework` propriedade para `net5.0-windows` .</span><span class="sxs-lookup"><span data-stu-id="37402-117">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="37402-118">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="37402-118">Affected APIs</span></span>

<span data-ttu-id="37402-119">Não detectável via análise de API.</span><span class="sxs-lookup"><span data-stu-id="37402-119">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
