---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031953"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a><span data-ttu-id="a3854-101">Não há suporte para a manipulação de exceções de estado corrompidas</span><span class="sxs-lookup"><span data-stu-id="a3854-101">Handling corrupted state exceptions is not supported</span></span>

<span data-ttu-id="a3854-102">Não há suporte para a manipulação de exceções de estado de processo corrompido no .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a3854-102">Handling corrupted-process-state exceptions in .NET Core is not supported.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a3854-103">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="a3854-103">Change description</span></span>

<span data-ttu-id="a3854-104">Anteriormente, as exceções de estado de processo corrompido poderiam ser detectadas e manipuladas por manipuladores de exceção de código gerenciado, por exemplo, usando uma instrução [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) em C#.</span><span class="sxs-lookup"><span data-stu-id="a3854-104">Previously, corrupted-process-state exceptions could be caught and handled by managed code exception handlers, for example, by using a [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) statement in C#.</span></span>

<span data-ttu-id="a3854-105">A partir do .NET Core 1,0, as exceções de estado de processo corrompido não podem ser manipuladas pelo código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="a3854-105">Starting in .NET Core 1.0, corrupted-process-state exceptions cannot be handled by managed code.</span></span> <span data-ttu-id="a3854-106">O Common Language Runtime não entrega exceções de estado de processo corrompidas ao código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="a3854-106">The common language runtime doesn't deliver corrupted-process-state exceptions to managed code.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a3854-107">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="a3854-107">Version introduced</span></span>

<span data-ttu-id="a3854-108">1.0</span><span class="sxs-lookup"><span data-stu-id="a3854-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a3854-109">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="a3854-109">Recommended action</span></span>

<span data-ttu-id="a3854-110">Evite a necessidade de lidar com exceções de estado de processo corrompido abordando as situações que levam a elas em vez disso.</span><span class="sxs-lookup"><span data-stu-id="a3854-110">Avoid the need to handle corrupted-process-state exceptions by addressing the situations that lead to them instead.</span></span> <span data-ttu-id="a3854-111">Se for absolutamente necessário manipular exceções de estado de processo corrompido, grave o manipulador de exceção em código C ou C++.</span><span class="sxs-lookup"><span data-stu-id="a3854-111">If it's absolutely necessary to handle corrupted-process-state exceptions, write the exception handler in C or C++ code.</span></span>

#### <a name="category"></a><span data-ttu-id="a3854-112">Categoria</span><span class="sxs-lookup"><span data-stu-id="a3854-112">Category</span></span>

<span data-ttu-id="a3854-113">Bibliotecas principais do .NET</span><span class="sxs-lookup"><span data-stu-id="a3854-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a3854-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="a3854-114">Affected APIs</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [<span data-ttu-id="a3854-115">Elemento legacyCorruptedStateExceptionsPolicy</span><span class="sxs-lookup"><span data-stu-id="a3854-115">legacyCorruptedStateExceptionsPolicy element</span></span>](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->
