---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032244"
---
### <a name="http-response-body-infrastructure-changes"></a><span data-ttu-id="274f4-101">HTTP: alterações de infraestrutura de corpo de resposta</span><span class="sxs-lookup"><span data-stu-id="274f4-101">HTTP: Response body infrastructure changes</span></span>

<span data-ttu-id="274f4-102">A infraestrutura que faz o backup de um corpo de resposta HTTP foi alterada.</span><span class="sxs-lookup"><span data-stu-id="274f4-102">The infrastructure backing an HTTP response body has changed.</span></span> <span data-ttu-id="274f4-103">Se você estiver usando `HttpResponse` diretamente, não deverá precisar fazer nenhuma alteração de código.</span><span class="sxs-lookup"><span data-stu-id="274f4-103">If you're using `HttpResponse` directly, you shouldn't need to make any code changes.</span></span> <span data-ttu-id="274f4-104">Leia mais detalhadamente se você estiver encapsulando ou substituindo `HttpResponse.Body` ou acessando `HttpContext.Features` .</span><span class="sxs-lookup"><span data-stu-id="274f4-104">Read further if you're wrapping or replacing `HttpResponse.Body` or accessing `HttpContext.Features`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="274f4-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="274f4-105">Version introduced</span></span>

<span data-ttu-id="274f4-106">3.0</span><span class="sxs-lookup"><span data-stu-id="274f4-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="274f4-107">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="274f4-107">Old behavior</span></span>

<span data-ttu-id="274f4-108">Havia três APIs associadas ao corpo da resposta HTTP:</span><span class="sxs-lookup"><span data-stu-id="274f4-108">There were three APIs associated with the HTTP response body:</span></span>

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a><span data-ttu-id="274f4-109">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="274f4-109">New behavior</span></span>

<span data-ttu-id="274f4-110">Se você substituir `HttpResponse.Body` , ele substituirá todo `IHttpResponseBodyFeature` com um wrapper em seu fluxo específico usando `StreamResponseBodyFeature` para fornecer implementações padrão para todas as APIs esperadas.</span><span class="sxs-lookup"><span data-stu-id="274f4-110">If you replace `HttpResponse.Body`, it replaces the entire `IHttpResponseBodyFeature` with a wrapper around your given stream using `StreamResponseBodyFeature` to provide default implementations for all of the expected APIs.</span></span> <span data-ttu-id="274f4-111">A configuração de volta do fluxo original reverte essa alteração.</span><span class="sxs-lookup"><span data-stu-id="274f4-111">Setting back the original stream reverts this change.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="274f4-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="274f4-112">Reason for change</span></span>

<span data-ttu-id="274f4-113">A motivação é combinar as APIs de corpo de resposta em uma única interface de recurso nova.</span><span class="sxs-lookup"><span data-stu-id="274f4-113">The motivation is to combine the response body APIs into a single new feature interface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="274f4-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="274f4-114">Recommended action</span></span>

<span data-ttu-id="274f4-115">Use o `IHttpResponseBodyFeature` local em que você estava usando anteriormente `IHttpResponseFeature.Body` , `IHttpSendFileFeature` , ou `IHttpBufferingFeature` .</span><span class="sxs-lookup"><span data-stu-id="274f4-115">Use `IHttpResponseBodyFeature` where you previously were using `IHttpResponseFeature.Body`, `IHttpSendFileFeature`, or `IHttpBufferingFeature`.</span></span>

#### <a name="category"></a><span data-ttu-id="274f4-116">Categoria</span><span class="sxs-lookup"><span data-stu-id="274f4-116">Category</span></span>

<span data-ttu-id="274f4-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="274f4-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="274f4-118">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="274f4-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
