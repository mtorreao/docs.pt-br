---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031955"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="76ce2-101">UnauthorizedAccessException gerado por FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="76ce2-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="76ce2-102">No .NET Core, um <xref:System.UnauthorizedAccessException> é gerado quando o chamador tenta definir um valor de atributo de arquivo, mas não tem permissão de gravação.</span><span class="sxs-lookup"><span data-stu-id="76ce2-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="76ce2-103">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="76ce2-103">Change description</span></span>

<span data-ttu-id="76ce2-104">No .NET Framework, um <xref:System.ArgumentException> é gerado quando o chamador tenta definir um valor de atributo de arquivo no <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> , mas não tem permissão de gravação.</span><span class="sxs-lookup"><span data-stu-id="76ce2-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="76ce2-105">No .NET Core, um <xref:System.UnauthorizedAccessException> é lançado em vez disso.</span><span class="sxs-lookup"><span data-stu-id="76ce2-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="76ce2-106">(No .NET Core, um <xref:System.ArgumentException> ainda será gerado se o chamador tentar definir um atributo de arquivo inválido.)</span><span class="sxs-lookup"><span data-stu-id="76ce2-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="76ce2-107">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="76ce2-107">Version introduced</span></span>

<span data-ttu-id="76ce2-108">1.0</span><span class="sxs-lookup"><span data-stu-id="76ce2-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="76ce2-109">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="76ce2-109">Recommended action</span></span>

<span data-ttu-id="76ce2-110">Modifique as `catch` instruções para capturar um <xref:System.UnauthorizedAccessException> em vez de, ou além de, um <xref:System.ArgumentException> , conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="76ce2-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="76ce2-111">Categoria</span><span class="sxs-lookup"><span data-stu-id="76ce2-111">Category</span></span>

<span data-ttu-id="76ce2-112">Bibliotecas principais do .NET</span><span class="sxs-lookup"><span data-stu-id="76ce2-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="76ce2-113">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="76ce2-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
