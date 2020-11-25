---
title: 'Alteração significativa: Kestrel: transporte Libuv marcado como obsoleto'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulado Kestrel: transporte Libuv marcado como obsoleto'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f66b9b646671e07957e6d30a95333d392eb29617
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760398"
---
# <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="86dfb-103">Kestrel: transporte Libuv marcado como obsoleto</span><span class="sxs-lookup"><span data-stu-id="86dfb-103">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="86dfb-104">As versões anteriores do ASP.NET Core usavam Libuv como um detalhe de implementação de como a entrada e a saída assíncronas foram executadas.</span><span class="sxs-lookup"><span data-stu-id="86dfb-104">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="86dfb-105">No ASP.NET Core 2,0, <xref:System.Net.Sockets.Socket> foi desenvolvido um transporte baseado em alternativa.</span><span class="sxs-lookup"><span data-stu-id="86dfb-105">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="86dfb-106">No ASP.NET Core 2,1, o Kestrel mudou para usar o `Socket` transporte baseado por padrão.</span><span class="sxs-lookup"><span data-stu-id="86dfb-106">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="86dfb-107">O suporte a Libuv foi mantido por motivos de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="86dfb-107">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="86dfb-108">Neste ponto, o uso do `Socket` transporte baseado é muito mais comum do que o transporte Libuv.</span><span class="sxs-lookup"><span data-stu-id="86dfb-108">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="86dfb-109">Consequentemente, o suporte a Libuv é marcado como obsoleto no .NET 5,0 e será totalmente removido no .NET 6,0.</span><span class="sxs-lookup"><span data-stu-id="86dfb-109">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="86dfb-110">Como parte dessa alteração, o suporte do Libuv para novas plataformas de sistema operacional (como o Windows ARM64) não será adicionado no período de tempo do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="86dfb-110">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="86dfb-111">Para obter uma discussão sobre problemas de bloqueio que exigem o uso do transporte Libuv, consulte o problema do GitHub em [dotnet/aspnetcore # 23409](https://github.com/dotnet/aspnetcore/issues/23409).</span><span class="sxs-lookup"><span data-stu-id="86dfb-111">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="86dfb-112">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="86dfb-112">Version introduced</span></span>

<span data-ttu-id="86dfb-113">5,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="86dfb-113">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="86dfb-114">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="86dfb-114">Old behavior</span></span>

<span data-ttu-id="86dfb-115">As APIs Libuv não são marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="86dfb-115">The Libuv APIs aren't marked as obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="86dfb-116">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="86dfb-116">New behavior</span></span>

<span data-ttu-id="86dfb-117">As APIs Libuv são marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="86dfb-117">The Libuv APIs are marked as obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="86dfb-118">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="86dfb-118">Reason for change</span></span>

<span data-ttu-id="86dfb-119">O `Socket` transporte baseado em é o padrão.</span><span class="sxs-lookup"><span data-stu-id="86dfb-119">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="86dfb-120">Não há nenhum motivo convincente para continuar usando o transporte Libuv.</span><span class="sxs-lookup"><span data-stu-id="86dfb-120">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="86dfb-121">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="86dfb-121">Recommended action</span></span>

<span data-ttu-id="86dfb-122">Descontinue o uso do [pacote Libuv](https://www.nuget.org/packages/Libuv) e dos métodos de extensão.</span><span class="sxs-lookup"><span data-stu-id="86dfb-122">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="86dfb-123">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="86dfb-123">Affected APIs</span></span>

- [<span data-ttu-id="86dfb-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="86dfb-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="86dfb-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="86dfb-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="86dfb-126">Microsoft. AspNetCore. Server. Kestrel. Transport. Libuv. LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="86dfb-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="86dfb-127">Microsoft. AspNetCore. Server. Kestrel. Transport. Libuv. LibuvTransportOptions. ThreadCount</span><span class="sxs-lookup"><span data-stu-id="86dfb-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="86dfb-128">Microsoft. AspNetCore. Server. Kestrel. Transport. Libuv. LibuvTransportOptions. NoDelay</span><span class="sxs-lookup"><span data-stu-id="86dfb-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="86dfb-129">Microsoft. AspNetCore. Server. Kestrel. Transport. Libuv. LibuvTransportOptions. MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="86dfb-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="86dfb-130">Microsoft. AspNetCore. Server. Kestrel. Transport. Libuv. LibuvTransportOptions. MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="86dfb-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
