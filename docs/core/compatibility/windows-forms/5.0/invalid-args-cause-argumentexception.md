---
title: 'Alteração significativa: os métodos WinForms agora lançam ArgumentException'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que os métodos de formulários sWindows agora geram argumentos inválidos.
ms.date: 07/18/2020
ms.openlocfilehash: 46fe3f3b1208a5cd676e1b7546507bed36a850f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760544"
---
# <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="ea888-103">Os métodos WinForms agora lançam ArgumentException</span><span class="sxs-lookup"><span data-stu-id="ea888-103">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="ea888-104">Alguns métodos de Windows Forms agora lançam um <xref:System.ArgumentException> para argumentos inválidos, onde anteriormente não fizeram isso.</span><span class="sxs-lookup"><span data-stu-id="ea888-104">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="ea888-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="ea888-105">Change description</span></span>

<span data-ttu-id="ea888-106">Anteriormente, passar argumentos de um tipo inesperado ou incorreto para determinados métodos de Windows Forms resultaria em um estado indeterminado.</span><span class="sxs-lookup"><span data-stu-id="ea888-106">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="ea888-107">A partir do .NET 5,0, esses métodos agora geram um <xref:System.ArgumentException> quando passaram argumentos inválidos.</span><span class="sxs-lookup"><span data-stu-id="ea888-107">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="ea888-108">Lançar um <xref:System.ArgumentException> está em conformidade com o comportamento do tempo de execução do .net.</span><span class="sxs-lookup"><span data-stu-id="ea888-108">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="ea888-109">Ele também melhora a experiência de depuração ao comunicar-se claramente qual argumento é inválido.</span><span class="sxs-lookup"><span data-stu-id="ea888-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ea888-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="ea888-110">Version introduced</span></span>

<span data-ttu-id="ea888-111">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="ea888-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ea888-112">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="ea888-112">Recommended action</span></span>

- <span data-ttu-id="ea888-113">Atualize o código para evitar a passagem de argumentos inválidos.</span><span class="sxs-lookup"><span data-stu-id="ea888-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="ea888-114">Se necessário, manipule um <xref:System.ArgumentException> ao chamar o método.</span><span class="sxs-lookup"><span data-stu-id="ea888-114">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ea888-115">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="ea888-115">Affected APIs</span></span>

<span data-ttu-id="ea888-116">A tabela a seguir lista os métodos e parâmetros afetados:</span><span class="sxs-lookup"><span data-stu-id="ea888-116">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="ea888-117">Método</span><span class="sxs-lookup"><span data-stu-id="ea888-117">Method</span></span> | <span data-ttu-id="ea888-118">Nome do parâmetro</span><span class="sxs-lookup"><span data-stu-id="ea888-118">Parameter name</span></span> | <span data-ttu-id="ea888-119">Condição</span><span class="sxs-lookup"><span data-stu-id="ea888-119">Condition</span></span> | <span data-ttu-id="ea888-120">Versão adicionada</span><span class="sxs-lookup"><span data-stu-id="ea888-120">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="ea888-121">O argumento não é do tipo <xref:System.Windows.Forms.TabPage> .</span><span class="sxs-lookup"><span data-stu-id="ea888-121">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="ea888-122">Preview 1</span><span class="sxs-lookup"><span data-stu-id="ea888-122">Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="ea888-123">Argumento é `null` , <xref:System.String.Empty?displayProperty=nameWithType> ou espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="ea888-123">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="ea888-124">Versão prévia 5</span><span class="sxs-lookup"><span data-stu-id="ea888-124">Preview 5</span></span> |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | <span data-ttu-id="ea888-125">Não é possível recuperar um `InputLanguage` para a cultura especificada.</span><span class="sxs-lookup"><span data-stu-id="ea888-125">Unable to retrieve an `InputLanguage` for the specified culture.</span></span> | <span data-ttu-id="ea888-126">Versão prévia 7</span><span class="sxs-lookup"><span data-stu-id="ea888-126">Preview 7</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

### Category

Windows Forms

-->
