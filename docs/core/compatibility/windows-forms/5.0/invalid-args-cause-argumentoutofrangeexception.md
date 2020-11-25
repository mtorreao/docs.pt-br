---
title: 'Alteração significativa: as propriedades do WinForms agora lançam ArgumentOutOfRangeException'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que algumas propriedades de Windows Forms agora lançam um ArgumentOutOfRangeException para argumentos inválidos.
ms.date: 06/18/2020
ms.openlocfilehash: 94593047d16304ce401b23993ad4ca173c10812b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760479"
---
# <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="082f2-103">As propriedades do WinForms agora geram ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="082f2-103">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="082f2-104">Algumas propriedades de Windows Forms agora lançam um <xref:System.ArgumentOutOfRangeException> para argumentos inválidos, onde anteriormente não.</span><span class="sxs-lookup"><span data-stu-id="082f2-104">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="082f2-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="082f2-105">Change description</span></span>

<span data-ttu-id="082f2-106">Anteriormente, essas propriedades lançavam várias exceções, como <xref:System.NullReferenceException> , <xref:System.IndexOutOfRangeException> ou, <xref:System.ArgumentException> quando passaram argumentos fora do intervalo.</span><span class="sxs-lookup"><span data-stu-id="082f2-106">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="082f2-107">A partir do .NET 5,0, essas propriedades agora lançam <xref:System.ArgumentOutOfRangeException> argumentos When passados que estão fora do intervalo.</span><span class="sxs-lookup"><span data-stu-id="082f2-107">Starting in .NET 5.0, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="082f2-108">Lançar um <xref:System.ArgumentOutOfRangeException> está em conformidade com o comportamento do tempo de execução do .net.</span><span class="sxs-lookup"><span data-stu-id="082f2-108">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="082f2-109">Ele também melhora a experiência de depuração ao comunicar-se claramente qual argumento é inválido.</span><span class="sxs-lookup"><span data-stu-id="082f2-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="082f2-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="082f2-110">Version introduced</span></span>

<span data-ttu-id="082f2-111">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="082f2-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="082f2-112">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="082f2-112">Recommended action</span></span>

- <span data-ttu-id="082f2-113">Atualize o código para evitar a passagem de argumentos inválidos.</span><span class="sxs-lookup"><span data-stu-id="082f2-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="082f2-114">Se necessário, manipule um <xref:System.ArgumentOutOfRangeException> ao definir a propriedade.</span><span class="sxs-lookup"><span data-stu-id="082f2-114">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="082f2-115">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="082f2-115">Affected APIs</span></span>

<span data-ttu-id="082f2-116">A tabela a seguir lista as propriedades e os parâmetros afetados:</span><span class="sxs-lookup"><span data-stu-id="082f2-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="082f2-117">Propriedade</span><span class="sxs-lookup"><span data-stu-id="082f2-117">Property</span></span> | <span data-ttu-id="082f2-118">Nome do parâmetro</span><span class="sxs-lookup"><span data-stu-id="082f2-118">Parameter name</span></span> | <span data-ttu-id="082f2-119">Versão adicionada</span><span class="sxs-lookup"><span data-stu-id="082f2-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="082f2-120">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="082f2-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="082f2-121">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="082f2-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="082f2-122">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="082f2-122">5.0 Preview 6</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

### Category

Windows Forms

-->
