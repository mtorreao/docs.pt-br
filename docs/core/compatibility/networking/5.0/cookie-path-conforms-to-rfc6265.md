---
title: 'Alteração significativa: o tratamento de caminho de cookie agora está em conformidade com RFC 6265'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que os algoritmos de tratamento de caminhos definidos na RFC 6265 foram implementados para as classes cookie e CookieContainer.
ms.date: 08/18/2020
ms.openlocfilehash: 4aea06f434c4bbbef7d94b4b39ff647dd954745e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760362"
---
# <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="e2379-103">O tratamento de caminho de cookie agora está em conformidade com RFC 6265</span><span class="sxs-lookup"><span data-stu-id="e2379-103">Cookie path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="e2379-104">Os algoritmos de tratamento de caminho definidos no [RFC 6265](https://tools.ietf.org/html/rfc6265) foram implementados para as <xref:System.Net.Cookie> <xref:System.Net.CookieContainer> classes e.</span><span class="sxs-lookup"><span data-stu-id="e2379-104">Path-handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for the <xref:System.Net.Cookie> and <xref:System.Net.CookieContainer> classes.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e2379-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="e2379-105">Version introduced</span></span>

<span data-ttu-id="e2379-106">5.0</span><span class="sxs-lookup"><span data-stu-id="e2379-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="e2379-107">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="e2379-107">Change description</span></span>

- <span data-ttu-id="e2379-108">A <xref:System.Net.Cookie.Path> propriedade não é mais necessária para ser um prefixo do caminho da solicitação.</span><span class="sxs-lookup"><span data-stu-id="e2379-108">The <xref:System.Net.Cookie.Path> property is no longer required to be a prefix of the request path.</span></span>
- <span data-ttu-id="e2379-109">O cálculo do valor padrão do <xref:System.Net.Cookie.Path> e dos algoritmos de correspondência de caminho foram implementados conforme definido na [seção 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) do RFC 6265.</span><span class="sxs-lookup"><span data-stu-id="e2379-109">The calculation of the default value of <xref:System.Net.Cookie.Path> and path-matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e2379-110">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="e2379-110">Recommended action</span></span>

<span data-ttu-id="e2379-111">Na maioria dos casos, você não precisará realizar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="e2379-111">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="e2379-112">No entanto, se o seu código depender da <xref:System.Net.Cookie.Path> validação, você precisará implementar a validação necessária em seu código.</span><span class="sxs-lookup"><span data-stu-id="e2379-112">However, if your code was dependent on <xref:System.Net.Cookie.Path> validation, you'll need to implement required validation in your code.</span></span> <span data-ttu-id="e2379-113">Se o seu código depender do cálculo do valor padrão para <xref:System.Net.Cookie.Path> , considere fornecer o <xref:System.Net.Cookie.Path> valor manualmente em vez de usar o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="e2379-113">If your code was dependent on default value calculation for <xref:System.Net.Cookie.Path>, consider supplying the <xref:System.Net.Cookie.Path> value manually instead of using the default value.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e2379-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="e2379-114">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

### Category

Networking

-->
