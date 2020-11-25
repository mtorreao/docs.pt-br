---
title: 'Alteração significativa: segurança: codificação de nome de cookie removido'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 título segurança: codificação de nome de cookie removido'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 3cd40d2b04d0cdf0863e3a3fb6d790c2b35692bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760532"
---
# <a name="security-cookie-name-encoding-removed"></a><span data-ttu-id="dd3b9-103">Segurança: codificação de nome de cookie removida</span><span class="sxs-lookup"><span data-stu-id="dd3b9-103">Security: Cookie name encoding removed</span></span>

<span data-ttu-id="dd3b9-104">O [padrão de cookie http](https://tools.ietf.org/html/rfc6265#section-4.1.1) permite apenas caracteres específicos em valores e nomes de cookie.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-104">The [HTTP cookie standard](https://tools.ietf.org/html/rfc6265#section-4.1.1) allows only specific characters in cookie names and values.</span></span> <span data-ttu-id="dd3b9-105">Para dar suporte a caracteres não permitidos, ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="dd3b9-105">To support disallowed characters, ASP.NET Core:</span></span>

* <span data-ttu-id="dd3b9-106">Codifica ao criar um cookie de resposta.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-106">Encodes when creating a response cookie.</span></span>
* <span data-ttu-id="dd3b9-107">Decodifica ao ler um cookie de solicitação.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-107">Decodes when reading a request cookie.</span></span>

<span data-ttu-id="dd3b9-108">No ASP.NET Core 5,0, esse comportamento de codificação mudou em resposta a uma preocupação de segurança.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-108">In ASP.NET Core 5.0, this encoding behavior changed in response to a security concern.</span></span>

<span data-ttu-id="dd3b9-109">Para obter uma discussão, consulte o problema do GitHub [dotnet/aspnetcore # 23578](https://github.com/dotnet/aspnetcore/issues/23578).</span><span class="sxs-lookup"><span data-stu-id="dd3b9-109">For discussion, see GitHub issue [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="dd3b9-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="dd3b9-110">Version introduced</span></span>

<span data-ttu-id="dd3b9-111">5,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="dd3b9-111">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="dd3b9-112">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="dd3b9-112">Old behavior</span></span>

<span data-ttu-id="dd3b9-113">Os nomes de cookies de resposta são codificados.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-113">Response cookie names are encoded.</span></span> <span data-ttu-id="dd3b9-114">Os nomes de cookie de solicitação são decodificados.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-114">Request cookie names are decoded.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="dd3b9-115">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="dd3b9-115">New behavior</span></span>

<span data-ttu-id="dd3b9-116">A codificação e a decodificação de nomes de cookies foram removidas.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-116">Encoding and decoding of cookie names was removed.</span></span> <span data-ttu-id="dd3b9-117">Para [versões anteriores com suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) do ASP.NET Core, a equipe planeja reduzir o problema de decodificação in-loco.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-117">For prior [supported versions](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) of ASP.NET Core, the team plans to mitigate the decoding issue in-place.</span></span> <span data-ttu-id="dd3b9-118">Além disso, chamar <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> com um nome de cookie inválido gera uma exceção do tipo <xref:System.ArgumentException> .</span><span class="sxs-lookup"><span data-stu-id="dd3b9-118">Additionally, calling <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> with an invalid cookie name throws an exception of type <xref:System.ArgumentException>.</span></span> <span data-ttu-id="dd3b9-119">A codificação e a decodificação de valores de cookies permanecem inalteradas.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-119">Encoding and decoding of cookie values remains unchanged.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="dd3b9-120">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="dd3b9-120">Reason for change</span></span>

<span data-ttu-id="dd3b9-121">Foi descoberto um problema em [várias estruturas da Web](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span><span class="sxs-lookup"><span data-stu-id="dd3b9-121">An issue was discovered in [multiple web frameworks](https://github.com/advisories/GHSA-j6w9-fv6q-3q52).</span></span> <span data-ttu-id="dd3b9-122">A codificação e a decodificação podem permitir que um invasor ignore um recurso de segurança chamado [prefixos de cookie](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) , falsificando prefixos reservados como `__Host-` com valores codificados como `__%48ost-` .</span><span class="sxs-lookup"><span data-stu-id="dd3b9-122">The encoding and decoding could allow an attacker to bypass a security feature called [cookie prefixes](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) by spoofing reserved prefixes like `__Host-` with encoded values like `__%48ost-`.</span></span> <span data-ttu-id="dd3b9-123">O ataque requer uma exploração secundária para injetar os cookies falsificados, como uma vulnerabilidade de XSS (script entre sites), no site.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-123">The attack requires a secondary exploit to inject the spoofed cookies, such as a cross-site scripting (XSS) vulnerability, in the website.</span></span> <span data-ttu-id="dd3b9-124">Esses prefixos não são usados por padrão em ASP.NET Core ou `Microsoft.Owin` bibliotecas ou modelos.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-124">These prefixes aren't used by default in ASP.NET Core or `Microsoft.Owin` libraries or templates.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="dd3b9-125">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="dd3b9-125">Recommended action</span></span>

<span data-ttu-id="dd3b9-126">Se você estiver movendo projetos para ASP.NET Core 5,0 ou posterior, verifique se seus nomes de cookie estão em conformidade com os [requisitos de especificação de token](https://tools.ietf.org/html/rfc2616#section-2.2): caracteres ASCII, excluindo controles e separadores `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT` .</span><span class="sxs-lookup"><span data-stu-id="dd3b9-126">If you're moving projects to ASP.NET Core 5.0 or later, ensure that their cookie names conform to the [token specification requirements](https://tools.ietf.org/html/rfc2616#section-2.2): ASCII characters excluding controls and separators `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`.</span></span> <span data-ttu-id="dd3b9-127">O uso de caracteres não ASCII em nomes de cookies ou outros cabeçalhos HTTP pode causar uma exceção do servidor ou ser de ida e volta inadequada pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="dd3b9-127">The use of non-ASCII characters in cookie names or other HTTP headers may cause an exception from the server or be improperly round-tripped by the client.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="dd3b9-128">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="dd3b9-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
