---
title: 'Alteração significativa: reconhecimento de URI de caminhos UNC no UNIX'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que a classe Uri agora reconhece cadeias de caracteres que começam com duas barras invertidas como caminhos UNC no UNIX.
ms.date: 11/01/2020
ms.openlocfilehash: 0d5d9cd8dd869f24e94d15724e5e16eaddf6ed47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760331"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="c2dac-103">Reconhecimento de URI de caminhos UNC no UNIX</span><span class="sxs-lookup"><span data-stu-id="c2dac-103">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="c2dac-104">A <xref:System.Uri> classe agora reconhece cadeias de caracteres que começam com duas barras ( `//` ) como caminhos UNC (Convenção de nomenclatura universal) em sistemas operacionais UNIX.</span><span class="sxs-lookup"><span data-stu-id="c2dac-104">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="c2dac-105">Essa alteração torna o comportamento de tais cadeias de caracteres consistentes em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="c2dac-105">This change makes the behavior for such strings consistent across all platforms.</span></span>

## <a name="change-description"></a><span data-ttu-id="c2dac-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="c2dac-106">Change description</span></span>

<span data-ttu-id="c2dac-107">Nas versões anteriores do .NET, a <xref:System.Uri> classe reconhece cadeias de caracteres que começam com duas barras "/", por exemplo, `//contoso` como caminhos de arquivo absolutos em sistemas operacionais UNIX.</span><span class="sxs-lookup"><span data-stu-id="c2dac-107">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="c2dac-108">No entanto, no Windows, essas cadeias de caracteres são reconhecidas como caminhos UNC.</span><span class="sxs-lookup"><span data-stu-id="c2dac-108">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="c2dac-109">A partir do .NET 5,0, a <xref:System.Uri> classe reconhece cadeias de caracteres que começam com duas barras invertidas como caminhos UNC em todas as plataformas, incluindo UNIX.</span><span class="sxs-lookup"><span data-stu-id="c2dac-109">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="c2dac-110">Além disso, as propriedades se comportam de acordo com a semântica UNC:</span><span class="sxs-lookup"><span data-stu-id="c2dac-110">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="c2dac-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> retorna `true`.</span><span class="sxs-lookup"><span data-stu-id="c2dac-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="c2dac-112">As barras invertidas no caminho são substituídas por barras "/".</span><span class="sxs-lookup"><span data-stu-id="c2dac-112">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="c2dac-113">Por exemplo, `//first\second` torna-se `//first/second`.</span><span class="sxs-lookup"><span data-stu-id="c2dac-113">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="c2dac-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType> Não codificar caracteres por porcentagem.</span><span class="sxs-lookup"><span data-stu-id="c2dac-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="c2dac-115">Por exemplo, `//first/\uFFF0` *não* é convertido em `//first/%EF%BF%B0` .</span><span class="sxs-lookup"><span data-stu-id="c2dac-115">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c2dac-116">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="c2dac-116">Version introduced</span></span>

<span data-ttu-id="c2dac-117">5.0</span><span class="sxs-lookup"><span data-stu-id="c2dac-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c2dac-118">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="c2dac-118">Recommended action</span></span>

<span data-ttu-id="c2dac-119">Nenhuma ação é necessária na parte do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="c2dac-119">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c2dac-120">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="c2dac-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
