---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032286"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a><span data-ttu-id="cdbbd-101">Kestrel: Solicitar cabeçalhos de trailer movidos para nova coleção</span><span class="sxs-lookup"><span data-stu-id="cdbbd-101">Kestrel: Request trailer headers moved to new collection</span></span>

<span data-ttu-id="cdbbd-102">Nas versões anteriores, Kestrel adicionou cabeçalhos de trailers de HTTP/1.1 na coleção de cabeçalhos de solicitação quando o corpo da solicitação foi lido até o final.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-102">In prior versions, Kestrel added HTTP/1.1 chunked trailer headers into the request headers collection when the request body was read to the end.</span></span> <span data-ttu-id="cdbbd-103">Esse comportamento causou preocupações sobre ambigüidade entre cabeçalhos e trailers.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-103">This behavior caused concerns about ambiguity between headers and trailers.</span></span> <span data-ttu-id="cdbbd-104">A decisão foi feita para mover os trailers para uma nova coleção.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-104">The decision was made to move the trailers to a new collection.</span></span>

<span data-ttu-id="cdbbd-105">Os trailers de solicitação HTTP/2 não estavam disponíveis no ASP.NET Core 2,2, mas agora também estão disponíveis nesta nova coleção no ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-105">HTTP/2 request trailers were unavailable in ASP.NET Core 2.2 but are now also available in this new collection in ASP.NET Core 3.0.</span></span>

<span data-ttu-id="cdbbd-106">Novos métodos de extensão de solicitação foram adicionados para acessar esses trailers.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-106">New request extension methods have been added to access these trailers.</span></span>

<span data-ttu-id="cdbbd-107">Os trailers HTTP/1.1 estão disponíveis quando todo o corpo da solicitação tiver sido lido.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-107">HTTP/1.1 trailers are available once the entire request body has been read.</span></span>

<span data-ttu-id="cdbbd-108">Os trailers HTTP/2 estão disponíveis quando são recebidos do cliente.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-108">HTTP/2 trailers are available once they're received from the client.</span></span> <span data-ttu-id="cdbbd-109">O cliente não enviará os trailers até que todo o corpo da solicitação tenha sido pelo menos armazenado em buffer pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-109">The client won't send the trailers until the entire request body has been at least buffered by the server.</span></span> <span data-ttu-id="cdbbd-110">Talvez seja necessário ler o corpo da solicitação para liberar espaço no buffer.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-110">You may need to read the request body to free up buffer space.</span></span> <span data-ttu-id="cdbbd-111">Os trailers sempre estarão disponíveis se você ler o corpo da solicitação para o final.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-111">Trailers are always available if you read the request body to the end.</span></span> <span data-ttu-id="cdbbd-112">Os marcadores marcam o fim do corpo.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-112">The trailers mark the end of the body.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cdbbd-113">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="cdbbd-113">Version introduced</span></span>

<span data-ttu-id="cdbbd-114">3.0</span><span class="sxs-lookup"><span data-stu-id="cdbbd-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cdbbd-115">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="cdbbd-115">Old behavior</span></span>

<span data-ttu-id="cdbbd-116">Os cabeçalhos do trailer de solicitação seriam adicionados à `HttpRequest.Headers` coleção.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-116">Request trailer headers would be added to the `HttpRequest.Headers` collection.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cdbbd-117">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="cdbbd-117">New behavior</span></span>

<span data-ttu-id="cdbbd-118">Os cabeçalhos de trailer de solicitação **não estão presentes** na `HttpRequest.Headers` coleção.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-118">Request trailer headers **aren't present** in the `HttpRequest.Headers` collection.</span></span> <span data-ttu-id="cdbbd-119">Use os seguintes métodos de extensão no `HttpRequest` para acessá-los:</span><span class="sxs-lookup"><span data-stu-id="cdbbd-119">Use the following extension methods on `HttpRequest` to access them:</span></span>

- <span data-ttu-id="cdbbd-120">`GetDeclaredTrailers()` -Obtém o cabeçalho "trailer" da solicitação que lista os marcadores a serem esperados após o corpo.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-120">`GetDeclaredTrailers()` - Gets the request "Trailer" header that lists which trailers to expect after the body.</span></span>
- <span data-ttu-id="cdbbd-121">`SupportsTrailers()` -Indica se a solicitação dá suporte ao recebimento de cabeçalhos de trailer.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-121">`SupportsTrailers()` - Indicates if the request supports receiving trailer headers.</span></span>
- <span data-ttu-id="cdbbd-122">`CheckTrailersAvailable()` -Determina se a solicitação dá suporte a trailers e se estão disponíveis para leitura.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-122">`CheckTrailersAvailable()` - Determines if the request supports trailers and if they're available for reading.</span></span>
- <span data-ttu-id="cdbbd-123">`GetTrailer(string trailerName)` -Obtém o cabeçalho à direita solicitado da resposta.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-123">`GetTrailer(string trailerName)` - Gets the requested trailing header from the response.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cdbbd-124">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="cdbbd-124">Reason for change</span></span>

<span data-ttu-id="cdbbd-125">Os trailers são um recurso importante em cenários como o gRPC.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-125">Trailers are a key feature in scenarios like gRPC.</span></span> <span data-ttu-id="cdbbd-126">Mesclar os trailers em cabeçalhos de solicitação era confuso para os usuários.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-126">Merging the trailers in to request headers was confusing to users.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cdbbd-127">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="cdbbd-127">Recommended action</span></span>

<span data-ttu-id="cdbbd-128">Use os métodos de extensão relacionados ao trailer no `HttpRequest` para acessar os trailers.</span><span class="sxs-lookup"><span data-stu-id="cdbbd-128">Use the trailer-related extension methods on `HttpRequest` to access trailers.</span></span>

#### <a name="category"></a><span data-ttu-id="cdbbd-129">Categoria</span><span class="sxs-lookup"><span data-stu-id="cdbbd-129">Category</span></span>

<span data-ttu-id="cdbbd-130">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdbbd-130">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cdbbd-131">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="cdbbd-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
