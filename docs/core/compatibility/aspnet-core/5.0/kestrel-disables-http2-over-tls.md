---
title: 'Alteração significativa: Kestrel: HTTP/2 desabilitado via TLS em versões incompatíveis do Windows'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulado Kestrel: HTTP/2 desabilitado em TLS em versões incompatíveis do Windows'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: befd393795f3e1859d391bca513dd9856101d295
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760482"
---
# <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a><span data-ttu-id="85538-103">Kestrel: HTTP/2 desabilitado via TLS em versões incompatíveis do Windows</span><span class="sxs-lookup"><span data-stu-id="85538-103">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>

<span data-ttu-id="85538-104">Para habilitar o HTTP/2 pela TLS (segurança da camada de transporte) no Windows, dois requisitos precisam ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="85538-104">To enable HTTP/2 over Transport Layer Security (TLS) on Windows, two requirements need to be met:</span></span>

- <span data-ttu-id="85538-105">Suporte à ALPN (negociação de protocolo Application-Layer), que está disponível a partir do Windows 8.1 e do Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="85538-105">Application-Layer Protocol Negotiation (ALPN) support, which is available starting with Windows 8.1 and Windows Server 2012 R2.</span></span>
- <span data-ttu-id="85538-106">Um conjunto de codificações compatível com HTTP/2, que está disponível a partir do Windows 10 e do Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="85538-106">A set of ciphers compatible with HTTP/2, which is available starting with Windows 10 and Windows Server 2016.</span></span>

<span data-ttu-id="85538-107">Dessa forma, o comportamento do Kestrel quando HTTP/2 sobre TLS é configurado foi alterado para:</span><span class="sxs-lookup"><span data-stu-id="85538-107">As such, Kestrel's behavior when HTTP/2 over TLS is configured has changed to:</span></span>

- <span data-ttu-id="85538-108">`Http1`Faça o downgrade para e registre uma mensagem no `Information` nível quando [ListenerOptions. HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) for definido como `Http1AndHttp2` .</span><span class="sxs-lookup"><span data-stu-id="85538-108">Downgrade to `Http1` and log a message at the `Information` level when [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) is set to `Http1AndHttp2`.</span></span> <span data-ttu-id="85538-109">`Http1AndHttp2` é o valor padrão do `ListenOptions.HttpProtocols`.</span><span class="sxs-lookup"><span data-stu-id="85538-109">`Http1AndHttp2` is the default value for `ListenOptions.HttpProtocols`.</span></span>
- <span data-ttu-id="85538-110">Lança um `NotSupportedException` quando `ListenOptions.HttpProtocols` é definido como `Http2` .</span><span class="sxs-lookup"><span data-stu-id="85538-110">Throw a `NotSupportedException` when `ListenOptions.HttpProtocols` is set to `Http2`.</span></span>

<span data-ttu-id="85538-111">Para obter uma discussão, veja Issue [dotnet/aspnetcore # 23068](https://github.com/dotnet/aspnetcore/issues/23068).</span><span class="sxs-lookup"><span data-stu-id="85538-111">For discussion, see issue [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="85538-112">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="85538-112">Version introduced</span></span>

<span data-ttu-id="85538-113">ASP.NET Core 5,0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="85538-113">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="85538-114">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="85538-114">Old behavior</span></span>

<span data-ttu-id="85538-115">A tabela a seguir descreve o comportamento quando HTTP/2 em TLS é configurado.</span><span class="sxs-lookup"><span data-stu-id="85538-115">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="85538-116">Protocolos</span><span class="sxs-lookup"><span data-stu-id="85538-116">Protocols</span></span> | <span data-ttu-id="85538-117">Windows 7,</span><span class="sxs-lookup"><span data-stu-id="85538-117">Windows 7,</span></span><br /><span data-ttu-id="85538-118">Windows Server 2008 R2,</span><span class="sxs-lookup"><span data-stu-id="85538-118">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="85538-119">ou anterior</span><span class="sxs-lookup"><span data-stu-id="85538-119">or earlier</span></span> | <span data-ttu-id="85538-120">Windows 8,</span><span class="sxs-lookup"><span data-stu-id="85538-120">Windows 8,</span></span><br /><span data-ttu-id="85538-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="85538-121">Windows Server 2012</span></span> | <span data-ttu-id="85538-122">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="85538-122">Windows 8.1,</span></span><br /><span data-ttu-id="85538-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="85538-123">Windows Server 2012 R2</span></span> | <span data-ttu-id="85538-124">Windows 10,</span><span class="sxs-lookup"><span data-stu-id="85538-124">Windows 10,</span></span><br /><span data-ttu-id="85538-125">Windows Server 2016,</span><span class="sxs-lookup"><span data-stu-id="85538-125">Windows Server 2016,</span></span><br /><span data-ttu-id="85538-126"> ou mais recente</span><span class="sxs-lookup"><span data-stu-id="85538-126">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="85538-127">Throw `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="85538-127">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="85538-128">Erro durante o handshake de TLS</span><span class="sxs-lookup"><span data-stu-id="85538-128">Error during TLS handshake</span></span>     | <span data-ttu-id="85538-129">Erro durante o handshake de TLS &ast;</span><span class="sxs-lookup"><span data-stu-id="85538-129">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="85538-130">Nenhum erro</span><span class="sxs-lookup"><span data-stu-id="85538-130">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="85538-131">Fazer downgrade para `Http1`</span><span class="sxs-lookup"><span data-stu-id="85538-131">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="85538-132">Fazer downgrade para `Http1`</span><span class="sxs-lookup"><span data-stu-id="85538-132">Downgrade to `Http1`</span></span>     | <span data-ttu-id="85538-133">Erro durante o handshake de TLS &ast;</span><span class="sxs-lookup"><span data-stu-id="85538-133">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="85538-134">Nenhum erro</span><span class="sxs-lookup"><span data-stu-id="85538-134">No error</span></span> |

<span data-ttu-id="85538-135">&ast; Configure conjuntos de codificação compatíveis para habilitar esses cenários.</span><span class="sxs-lookup"><span data-stu-id="85538-135">&ast; Configure compatible cipher suites to enable these scenarios.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="85538-136">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="85538-136">New behavior</span></span>

<span data-ttu-id="85538-137">A tabela a seguir descreve o comportamento quando HTTP/2 em TLS é configurado.</span><span class="sxs-lookup"><span data-stu-id="85538-137">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="85538-138">Protocolos</span><span class="sxs-lookup"><span data-stu-id="85538-138">Protocols</span></span> | <span data-ttu-id="85538-139">Windows 7,</span><span class="sxs-lookup"><span data-stu-id="85538-139">Windows 7,</span></span><br /><span data-ttu-id="85538-140">Windows Server 2008 R2,</span><span class="sxs-lookup"><span data-stu-id="85538-140">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="85538-141">ou anterior</span><span class="sxs-lookup"><span data-stu-id="85538-141">or earlier</span></span> | <span data-ttu-id="85538-142">Windows 8,</span><span class="sxs-lookup"><span data-stu-id="85538-142">Windows 8,</span></span><br /><span data-ttu-id="85538-143">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="85538-143">Windows Server 2012</span></span> | <span data-ttu-id="85538-144">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="85538-144">Windows 8.1,</span></span><br /><span data-ttu-id="85538-145">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="85538-145">Windows Server 2012 R2</span></span> | <span data-ttu-id="85538-146">Windows 10,</span><span class="sxs-lookup"><span data-stu-id="85538-146">Windows 10,</span></span><br /><span data-ttu-id="85538-147">Windows Server 2016,</span><span class="sxs-lookup"><span data-stu-id="85538-147">Windows Server 2016,</span></span><br /><span data-ttu-id="85538-148"> ou mais recente</span><span class="sxs-lookup"><span data-stu-id="85538-148">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="85538-149">Throw `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="85538-149">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="85538-150">Throw `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="85538-150">Throw `NotSupportedException`</span></span>     | <span data-ttu-id="85538-151">Lançar `NotSupportedException`&ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="85538-151">Throw `NotSupportedException` &ast;&ast;</span></span>     | <span data-ttu-id="85538-152">Nenhum erro</span><span class="sxs-lookup"><span data-stu-id="85538-152">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="85538-153">Fazer downgrade para `Http1`</span><span class="sxs-lookup"><span data-stu-id="85538-153">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="85538-154">Fazer downgrade para `Http1`</span><span class="sxs-lookup"><span data-stu-id="85538-154">Downgrade to `Http1`</span></span>     | <span data-ttu-id="85538-155">Fazer downgrade para `Http1`&ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="85538-155">Downgrade to `Http1` &ast;&ast;</span></span>     | <span data-ttu-id="85538-156">Nenhum erro</span><span class="sxs-lookup"><span data-stu-id="85538-156">No error</span></span> |

<span data-ttu-id="85538-157">&ast;&ast; Configure conjuntos de codificação compatíveis e defina a opção de contexto do aplicativo `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` como `true` para habilitar esses cenários.</span><span class="sxs-lookup"><span data-stu-id="85538-157">&ast;&ast; Configure compatible cipher suites and set the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` to `true` to enable these scenarios.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="85538-158">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="85538-158">Reason for change</span></span>

<span data-ttu-id="85538-159">Essa alteração garante que os erros de compatibilidade para HTTP/2 sobre TLS em versões mais antigas do Windows sejam exibidos como antes e o mais claramente possível.</span><span class="sxs-lookup"><span data-stu-id="85538-159">This change ensures compatibility errors for HTTP/2 over TLS on older Windows versions are surfaced as early and as clearly as possible.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="85538-160">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="85538-160">Recommended action</span></span>

<span data-ttu-id="85538-161">Verifique se o HTTP/2 sobre TLS está desabilitado em versões incompatíveis do Windows.</span><span class="sxs-lookup"><span data-stu-id="85538-161">Ensure HTTP/2 over TLS is disabled on incompatible Windows versions.</span></span> <span data-ttu-id="85538-162">O Windows 8.1 e o Windows Server 2012 R2 são incompatíveis, pois não têm as codificações necessárias por padrão.</span><span class="sxs-lookup"><span data-stu-id="85538-162">Windows 8.1 and Windows Server 2012 R2 are incompatible since they lack the necessary ciphers by default.</span></span> <span data-ttu-id="85538-163">No entanto, é possível atualizar as definições de configuração do computador para usar codificações compatíveis com HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="85538-163">However, it's possible to update the Computer Configuration settings to use HTTP/2 compatible ciphers.</span></span> <span data-ttu-id="85538-164">Para obter mais informações, consulte [conjuntos de criptografia TLS em Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span><span class="sxs-lookup"><span data-stu-id="85538-164">For more information, see [TLS cipher suites in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span></span> <span data-ttu-id="85538-165">Uma vez configurado, o HTTP/2 sobre TLS em Kestrel deve ser habilitado definindo a opção de contexto do aplicativo `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` .</span><span class="sxs-lookup"><span data-stu-id="85538-165">Once configured, HTTP/2 over TLS on Kestrel must be enabled by setting the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`.</span></span> <span data-ttu-id="85538-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="85538-166">For example:</span></span>

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

<span data-ttu-id="85538-167">Nenhum suporte subjacente foi alterado.</span><span class="sxs-lookup"><span data-stu-id="85538-167">No underlying support has changed.</span></span> <span data-ttu-id="85538-168">Por exemplo, HTTP/2 sobre TLS nunca funcionou no Windows 8 ou no Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="85538-168">For example, HTTP/2 over TLS has never worked on Windows 8 or Windows Server 2012.</span></span> <span data-ttu-id="85538-169">Essa alteração modifica como os erros nesses cenários sem suporte são apresentados.</span><span class="sxs-lookup"><span data-stu-id="85538-169">This change modifies how errors in these unsupported scenarios are presented.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="85538-170">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="85538-170">Affected APIs</span></span>

<span data-ttu-id="85538-171">Nenhum</span><span class="sxs-lookup"><span data-stu-id="85538-171">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
