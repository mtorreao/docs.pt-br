---
title: 'Alteração significativa: os tipos mais recentes: JSObjectReference e JSInProcessObjectReference foram alterados para interno'
description: 'Saiba mais sobre as alterações significativas no ASP.NET Core 5,0 intitulados mais recentes: JSObjectReference e JSInProcessObjectReference tipos alterados para interno'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 43a66d204f8309dc5afc57d099b2201c477cc3ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760379"
---
# <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="52072-103">Mais de: JSObjectReference e tipos JSInProcessObjectReference alterados para interno</span><span class="sxs-lookup"><span data-stu-id="52072-103">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="52072-104">Os novos `Microsoft.JSInterop.JSObjectReference` e os `Microsoft.JSInterop.JSInProcessObjectReference` tipos introduzidos no ASP.NET Core 5,0 RC1 foram marcados como `internal` .</span><span class="sxs-lookup"><span data-stu-id="52072-104">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="52072-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="52072-105">Version introduced</span></span>

<span data-ttu-id="52072-106">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="52072-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="52072-107">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="52072-107">Old behavior</span></span>

<span data-ttu-id="52072-108">Um `JSObjectReference` pode ser obtido de uma chamada de interoperabilidade JavaScript por meio do `IJSRuntime` .</span><span class="sxs-lookup"><span data-stu-id="52072-108">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="52072-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="52072-109">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

## <a name="new-behavior"></a><span data-ttu-id="52072-110">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="52072-110">New behavior</span></span>

<span data-ttu-id="52072-111">`JSObjectReference` usa o modificador de acesso [interno](../../../../csharp/language-reference/keywords/internal.md) .</span><span class="sxs-lookup"><span data-stu-id="52072-111">`JSObjectReference` uses the [internal](../../../../csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="52072-112">A `public` `IJSObjectReference` interface deve ser usada em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="52072-112">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="52072-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="52072-113">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="52072-114">`JSInProcessObjectReference` também foi marcado como `internal` e foi substituído por `IJSInProcessObjectReference` .</span><span class="sxs-lookup"><span data-stu-id="52072-114">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="52072-115">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="52072-115">Reason for change</span></span>

<span data-ttu-id="52072-116">A alteração torna o recurso de interoperabilidade JavaScript mais consistente com outros padrões no mais baixo.</span><span class="sxs-lookup"><span data-stu-id="52072-116">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="52072-117">`IJSObjectReference` é análogo a `IJSRuntime` , pois ele atende a uma finalidade semelhante e tem métodos e extensões semelhantes.</span><span class="sxs-lookup"><span data-stu-id="52072-117">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="52072-118">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="52072-118">Recommended action</span></span>

<span data-ttu-id="52072-119">Substituir ocorrências de `JSObjectReference` e `JSInProcessObjectReference` por `IJSObjectReference` e `IJSInProcessObjectReference` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="52072-119">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="52072-120">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="52072-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
