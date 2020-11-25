---
title: 'Alteração significativa: HttpS: renegociação de certificado de cliente desabilitada por padrão'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulado HttpS: renegociação de certificado de cliente desabilitada por padrão'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 796989e1a21e3cb206d081e4fe8f79630121dc84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760313"
---
# <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a><span data-ttu-id="94fd7-103">HttpS: renegociação de certificado de cliente desabilitada por padrão</span><span class="sxs-lookup"><span data-stu-id="94fd7-103">HttpSys: Client certificate renegotiation disabled by default</span></span>

<span data-ttu-id="94fd7-104">A opção para renegociar uma conexão e solicitar um certificado de cliente foi desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="94fd7-104">The option to renegotiate a connection and request a client certificate has been disabled by default.</span></span> <span data-ttu-id="94fd7-105">Para obter uma discussão, veja Issue [dotnet/aspnetcore # 23181](https://github.com/dotnet/aspnetcore/issues/23181).</span><span class="sxs-lookup"><span data-stu-id="94fd7-105">For discussion, see issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="94fd7-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="94fd7-106">Version introduced</span></span>

<span data-ttu-id="94fd7-107">ASP.NET Core 5,0</span><span class="sxs-lookup"><span data-stu-id="94fd7-107">ASP.NET Core 5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="94fd7-108">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="94fd7-108">Old behavior</span></span>

<span data-ttu-id="94fd7-109">A conexão pode ser renegociada para solicitar um certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="94fd7-109">The connection can be renegotiated to request a client certificate.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="94fd7-110">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="94fd7-110">New behavior</span></span>

<span data-ttu-id="94fd7-111">Certificados de cliente só podem ser solicitados durante o handshake de conexão inicial.</span><span class="sxs-lookup"><span data-stu-id="94fd7-111">Client certificates can only be requested during the initial connection handshake.</span></span> <span data-ttu-id="94fd7-112">Para obter mais informações, consulte solicitação pull [dotnet/aspnetcore # 23162](https://github.com/dotnet/aspnetcore/pull/23162).</span><span class="sxs-lookup"><span data-stu-id="94fd7-112">For more information, see pull request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="94fd7-113">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="94fd7-113">Reason for change</span></span>

<span data-ttu-id="94fd7-114">A renegociação causou um número de problemas de desempenho e deadlock.</span><span class="sxs-lookup"><span data-stu-id="94fd7-114">Renegotiation caused a number of performance and deadlock issues.</span></span> <span data-ttu-id="94fd7-115">Também não tem suporte no HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="94fd7-115">It's also not supported in HTTP/2.</span></span> <span data-ttu-id="94fd7-116">Para obter o contexto adicional de quando a opção para controlar esse comportamento foi introduzida no ASP.NET Core 3,1, veja o problema [dotnet/aspnetcore # 14806](https://github.com/dotnet/aspnetcore/issues/14806).</span><span class="sxs-lookup"><span data-stu-id="94fd7-116">For additional context from when the option to control this behavior was introduced in ASP.NET Core 3.1, see issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="94fd7-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="94fd7-117">Recommended action</span></span>

<span data-ttu-id="94fd7-118">Aplicativos que exigem certificados de cliente devem usar *netsh.exe* para definir a `clientcertnegotiation` opção como `enabled` .</span><span class="sxs-lookup"><span data-stu-id="94fd7-118">Apps that require client certificates should use *netsh.exe* to set the `clientcertnegotiation` option to `enabled`.</span></span> <span data-ttu-id="94fd7-119">Para obter mais informações, consulte [netsh http Commands](/windows-server/networking/technologies/netsh/netsh-http).</span><span class="sxs-lookup"><span data-stu-id="94fd7-119">For more information, see [netsh http commands](/windows-server/networking/technologies/netsh/netsh-http).</span></span>

<span data-ttu-id="94fd7-120">Se você quiser que os certificados de cliente estejam habilitados somente para algumas partes do seu aplicativo, consulte as diretrizes em [certificados de cliente opcionais](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span><span class="sxs-lookup"><span data-stu-id="94fd7-120">If you want client certificates enabled for only some parts of your app, see the guidance at [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span></span>

<span data-ttu-id="94fd7-121">Se você precisar do comportamento antigo de renegociação, defina `HttpSysOptions.ClientCertificateMethod` como o valor antigo `ClientCertificateMethod.AllowRenegotiate` .</span><span class="sxs-lookup"><span data-stu-id="94fd7-121">If you need the old renegotiate behavior, set `HttpSysOptions.ClientCertificateMethod` to the old value `ClientCertificateMethod.AllowRenegotiate`.</span></span> <span data-ttu-id="94fd7-122">Isso não é recomendado pelos motivos descritos acima e nas diretrizes vinculadas.</span><span class="sxs-lookup"><span data-stu-id="94fd7-122">This isn't recommended for the reasons outlined above and in the linked guidance.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="94fd7-123">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="94fd7-123">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
