---
title: 'Alteração significativa: OutputType definido como WinExe para aplicativos WPF e WinForms'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que OutputType é definido automaticamente como WinExe para aplicativos Windows Forms.
ms.date: 09/18/2020
ms.openlocfilehash: 072c5b11c8304eb540e176ce9747930789f28505
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760528"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="461fe-103">OutputType definido como WinExe para aplicativos WPF e WinForms</span><span class="sxs-lookup"><span data-stu-id="461fe-103">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="461fe-104">`OutputType` é definido automaticamente como `WinExe` para Windows Presentation Foundation (WPF) e Windows Forms aplicativos.</span><span class="sxs-lookup"><span data-stu-id="461fe-104">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="461fe-105">Quando `OutputType` é definido como `WinExe` , uma janela do console não é aberta quando o aplicativo é executado.</span><span class="sxs-lookup"><span data-stu-id="461fe-105">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

## <a name="change-description"></a><span data-ttu-id="461fe-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="461fe-106">Change description</span></span>

<span data-ttu-id="461fe-107">Nas versões anteriores do .NET, o valor especificado para `OutputType` no arquivo de projeto é usado.</span><span class="sxs-lookup"><span data-stu-id="461fe-107">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="461fe-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="461fe-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="461fe-109">A partir do .NET 5,0, `OutputType` é definido automaticamente como `WinExe` para aplicativos do WPF e Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="461fe-109">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="461fe-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="461fe-110">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a><span data-ttu-id="461fe-111">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="461fe-111">Reason for change</span></span>

<span data-ttu-id="461fe-112">Supõe-se que a maioria dos usuários não queira que uma janela do console seja aberta quando um aplicativo do WPF ou Windows Forms é executado.</span><span class="sxs-lookup"><span data-stu-id="461fe-112">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="461fe-113">Além disso, [agora que esses tipos de aplicativos usam o SDK do .net](sdk-and-target-framework-change.md) em vez do SDK de área de trabalho do Windows, o padrão correto será definido.</span><span class="sxs-lookup"><span data-stu-id="461fe-113">In addition, [now that these application types use the .NET SDK](sdk-and-target-framework-change.md) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="461fe-114">Além disso, quando o suporte para o destino do iOS e do Android for adicionado, será mais fácil realizar vários destinos entre várias plataformas se todos usarem o mesmo tipo de saída.</span><span class="sxs-lookup"><span data-stu-id="461fe-114">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="461fe-115">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="461fe-115">Version introduced</span></span>

<span data-ttu-id="461fe-116">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="461fe-116">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="461fe-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="461fe-117">Recommended action</span></span>

<span data-ttu-id="461fe-118">Nenhuma ação é necessária em sua parte.</span><span class="sxs-lookup"><span data-stu-id="461fe-118">No action is required in your part.</span></span> <span data-ttu-id="461fe-119">No entanto, se você quiser reverter para o comportamento antigo, defina a `DisableWinExeOutputInference` propriedade como `true` em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="461fe-119">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a><span data-ttu-id="461fe-120">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="461fe-120">Affected APIs</span></span>

<span data-ttu-id="461fe-121">Não detectável via análise de API.</span><span class="sxs-lookup"><span data-stu-id="461fe-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
