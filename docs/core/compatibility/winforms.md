---
title: Windows Forms alterações significativas
description: Lista as alterações significativas em Windows Forms para .NET Core 3,0 e 3,1.
ms.date: 09/08/2020
ms.openlocfilehash: b944f7eea89b61f41feb8eef99e949c2d6017960
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726425"
---
# <a name="breaking-changes-in-windows-forms-for-net-core-30-and-31"></a><span data-ttu-id="a1029-103">Alterações recentes em Windows Forms para .NET Core 3,0 e 3,1</span><span class="sxs-lookup"><span data-stu-id="a1029-103">Breaking changes in Windows Forms for .NET Core 3.0 and 3.1</span></span>

<span data-ttu-id="a1029-104">Windows Forms suporte foi adicionado ao .NET Core na versão 3,0.</span><span class="sxs-lookup"><span data-stu-id="a1029-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="a1029-105">Este artigo lista as alterações significativas para Windows Forms pela versão do .NET na qual elas foram introduzidas.</span><span class="sxs-lookup"><span data-stu-id="a1029-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="a1029-106">Se você estiver atualizando um aplicativo Windows Forms de .NET Framework ou de uma versão anterior do .NET Core (3,0 ou posterior), este artigo se aplicará a você.</span><span class="sxs-lookup"><span data-stu-id="a1029-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="a1029-107">As seguintes alterações significativas estão documentadas nesta página:</span><span class="sxs-lookup"><span data-stu-id="a1029-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a1029-108">Alteração significativa</span><span class="sxs-lookup"><span data-stu-id="a1029-108">Breaking change</span></span> | <span data-ttu-id="a1029-109">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="a1029-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="a1029-110">Controles removidos</span><span class="sxs-lookup"><span data-stu-id="a1029-110">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="a1029-111">3.1</span><span class="sxs-lookup"><span data-stu-id="a1029-111">3.1</span></span> |
| [<span data-ttu-id="a1029-112">Evento CellFormatting não gerado se ToolTip for mostrado</span><span class="sxs-lookup"><span data-stu-id="a1029-112">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="a1029-113">3.1</span><span class="sxs-lookup"><span data-stu-id="a1029-113">3.1</span></span> |
| [<span data-ttu-id="a1029-114">Control. DefaultFont alterado para Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="a1029-114">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="a1029-115">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-115">3.0</span></span> |
| [<span data-ttu-id="a1029-116">Modernização do FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="a1029-116">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="a1029-117">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-117">3.0</span></span> |
| [<span data-ttu-id="a1029-118">SerializableAttribute removido de alguns tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1029-118">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="a1029-119">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-119">3.0</span></span> |
| [<span data-ttu-id="a1029-120">Não há suporte para a opção de compatibilidade AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="a1029-120">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="a1029-121">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-121">3.0</span></span> |
| [<span data-ttu-id="a1029-122">Não há suporte para a opção de compatibilidade DomainUpDown. UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="a1029-122">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="a1029-123">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-123">3.0</span></span> |
| [<span data-ttu-id="a1029-124">Não há suporte para a opção de compatibilidade DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="a1029-124">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="a1029-125">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-125">3.0</span></span> |
| [<span data-ttu-id="a1029-126">Não há suporte para a opção de compatibilidade DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="a1029-126">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="a1029-127">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-127">3.0</span></span> |
| [<span data-ttu-id="a1029-128">Não há suporte para a opção de compatibilidade DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="a1029-128">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="a1029-129">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-129">3.0</span></span> |
| [<span data-ttu-id="a1029-130">Não há suporte para a opção de compatibilidade EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="a1029-130">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="a1029-131">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-131">3.0</span></span> |
| [<span data-ttu-id="a1029-132">Não há suporte para a opção de compatibilidade UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="a1029-132">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="a1029-133">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-133">3.0</span></span> |
| [<span data-ttu-id="a1029-134">Não há suporte para a opção de compatibilidade UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="a1029-134">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="a1029-135">3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-135">3.0</span></span> |

## <a name="net-core-31"></a><span data-ttu-id="a1029-136">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a1029-136">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

<span data-ttu-id="a1029-137">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a1029-137">\*\*_</span></span>

## <a name="net-core-30"></a><span data-ttu-id="a1029-138">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a1029-138">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

_*_

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

_*_

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

<span data-ttu-id="a1029-139">_\*\*</span><span class="sxs-lookup"><span data-stu-id="a1029-139">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="a1029-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="a1029-140">See also</span></span>

- [<span data-ttu-id="a1029-141">Porta um aplicativo de Windows Forms para o .NET Core</span><span class="sxs-lookup"><span data-stu-id="a1029-141">Port a Windows Forms app to .NET Core</span></span>](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
