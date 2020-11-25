---
title: 'Alteração significativa: middleware: o middleware do manipulador de exceção lançará a exceção original se o manipulador não for encontrado'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulado middleware: o middleware do manipulador de exceção lança uma exceção original se o manipulador não for encontrado'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 8801d3e6950d66fd9f24e051fd8729c50eb0b282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760514"
---
# <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="61a09-103">Middleware: o middleware do manipulador de exceção lança a exceção original se o manipulador não for encontrado</span><span class="sxs-lookup"><span data-stu-id="61a09-103">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="61a09-104">Antes de ASP.NET Core 5,0, o [middleware do manipulador de exceção](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executa o manipulador de exceção configurado quando uma exceção ocorreu.</span><span class="sxs-lookup"><span data-stu-id="61a09-104">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="61a09-105">Se o manipulador de exceção, configurado via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> , não puder ser encontrado, uma resposta HTTP 404 será produzida.</span><span class="sxs-lookup"><span data-stu-id="61a09-105">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="61a09-106">A resposta é enganosa, pois:</span><span class="sxs-lookup"><span data-stu-id="61a09-106">The response is misleading in that it:</span></span>

* <span data-ttu-id="61a09-107">Parece ser um erro de usuário.</span><span class="sxs-lookup"><span data-stu-id="61a09-107">Seems to be a user error.</span></span>
* <span data-ttu-id="61a09-108">Obscurece o fato de que uma exceção ocorreu no servidor.</span><span class="sxs-lookup"><span data-stu-id="61a09-108">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="61a09-109">Para resolver o erro enganoso no ASP.NET Core 5,0, o `ExceptionHandlerMiddleware` lançará a exceção original se o manipulador de exceção não puder ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="61a09-109">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="61a09-110">Como resultado, uma resposta HTTP 500 é produzida pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="61a09-110">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="61a09-111">A resposta será mais fácil de examinar nos logs do servidor ao depurar o erro ocorrido.</span><span class="sxs-lookup"><span data-stu-id="61a09-111">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="61a09-112">Para obter uma discussão, consulte o problema do GitHub [dotnet/aspnetcore # 25288](https://github.com/dotnet/aspnetcore/issues/25288).</span><span class="sxs-lookup"><span data-stu-id="61a09-112">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="61a09-113">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="61a09-113">Version introduced</span></span>

<span data-ttu-id="61a09-114">5,0 RC 1</span><span class="sxs-lookup"><span data-stu-id="61a09-114">5.0 RC 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="61a09-115">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="61a09-115">Old behavior</span></span>

<span data-ttu-id="61a09-116">O middleware do manipulador de exceção produz uma resposta HTTP 404 se o manipulador de exceção configurado não puder ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="61a09-116">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="61a09-117">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="61a09-117">New behavior</span></span>

<span data-ttu-id="61a09-118">O middleware do manipulador de exceção lançará a exceção original se o manipulador de exceção configurado não puder ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="61a09-118">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="61a09-119">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="61a09-119">Reason for change</span></span>

<span data-ttu-id="61a09-120">O erro HTTP 404 não torna óbvio que ocorreu uma exceção no servidor.</span><span class="sxs-lookup"><span data-stu-id="61a09-120">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="61a09-121">Essa alteração produz um erro HTTP 500 para deixá-lo óbvio que:</span><span class="sxs-lookup"><span data-stu-id="61a09-121">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="61a09-122">O problema não é causado por um erro do usuário.</span><span class="sxs-lookup"><span data-stu-id="61a09-122">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="61a09-123">Exceção encontrada no servidor.</span><span class="sxs-lookup"><span data-stu-id="61a09-123">An exception was encountered on the server.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="61a09-124">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="61a09-124">Recommended action</span></span>

<span data-ttu-id="61a09-125">Não há nenhuma alteração de API.</span><span class="sxs-lookup"><span data-stu-id="61a09-125">There are no API changes.</span></span> <span data-ttu-id="61a09-126">Todos os aplicativos existentes continuarão a ser compilados e executados.</span><span class="sxs-lookup"><span data-stu-id="61a09-126">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="61a09-127">A exceção gerada é tratada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="61a09-127">The exception thrown is handled by the server.</span></span> <span data-ttu-id="61a09-128">Por exemplo, a exceção é convertida em uma resposta de erro HTTP 500 por [Kestrel](/aspnet/core/fundamentals/servers/kestrel) ou [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span><span class="sxs-lookup"><span data-stu-id="61a09-128">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="61a09-129">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="61a09-129">Affected APIs</span></span>

<span data-ttu-id="61a09-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="61a09-130">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
