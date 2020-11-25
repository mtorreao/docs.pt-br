---
title: 'Alteração significativa: NegotiateStream e SslStream permitem operações de início sucessivas'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que os casos de erro nos fluxos de segurança são tratados de forma diferente e as chamadas sucessivas para BeginAuthenticateAsServer ou BeginAuthenticateAsClient podem não falhar mais.
ms.date: 10/18/2020
ms.openlocfilehash: e0226d0f5586efca050ca3497ca1490fa21fd943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760356"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="fb39c-103">NegotiateStream e SslStream permitem operações de início sucessivas</span><span class="sxs-lookup"><span data-stu-id="fb39c-103">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="fb39c-104">Casos de erro em fluxos de segurança são tratados de forma diferente e chamadas sucessivas para `BeginAuthenticateAsServer` ou `BeginAuthenticateAsClient` podem não falhar mais.</span><span class="sxs-lookup"><span data-stu-id="fb39c-104">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="fb39c-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="fb39c-105">Version introduced</span></span>

<span data-ttu-id="fb39c-106">5.0</span><span class="sxs-lookup"><span data-stu-id="fb39c-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="fb39c-107">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="fb39c-107">Change description</span></span>

<span data-ttu-id="fb39c-108">Nas versões anteriores do .NET, chamando `BeginAuthenticateAsServer` ou `BeginAuthenticateAsClient` sucessivamente sem primeiro chamar `EndAuthenticateAsServer` ou `EndAuthenticateAsClient` resultar em um <xref:System.NotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="fb39c-108">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="fb39c-109">A partir do .NET 5,0, as chamadas sucessivas `BeginAuthenticateAsServer` ou `BeginAuthenticateAsClient` não resultam mais em um <xref:System.NotSupportedException> , pois essas APIs são apoiadas por uma <xref:System.Threading.Tasks.Task> implementação baseada em.</span><span class="sxs-lookup"><span data-stu-id="fb39c-109">Starting in .NET 5.0, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="fb39c-110">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="fb39c-110">Reason for change</span></span>

<span data-ttu-id="fb39c-111">Alternar a implementação interna do modelo de programação assíncrona (APM) para <xref:System.Threading.Tasks.Task> com base melhora o desempenho e diminui a complexidade do código.</span><span class="sxs-lookup"><span data-stu-id="fb39c-111">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="fb39c-112">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="fb39c-112">Recommended action</span></span>

<span data-ttu-id="fb39c-113">Nenhuma ação é necessária na parte do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="fb39c-113">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="fb39c-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="fb39c-114">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

### Category

Networking

-->
