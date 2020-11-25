---
title: 'Alteração significativa: Socket. LocalEndPoint é atualizado após chamar SendToAsync'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que o SendToAsync agora atualiza o valor da propriedade ponto de extremidade local para o endereço local do soquete.
ms.date: 10/18/2020
ms.openlocfilehash: 53d7da350eac6e65832012331044427fd90fe796
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760359"
---
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="12f58-103">Socket. LocalEndPoint é atualizado após chamar SendToAsync</span><span class="sxs-lookup"><span data-stu-id="12f58-103">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="12f58-104"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> Agora atualiza o valor da <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> propriedade para o endereço local do soquete.</span><span class="sxs-lookup"><span data-stu-id="12f58-104"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="12f58-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="12f58-105">Version introduced</span></span>

<span data-ttu-id="12f58-106">5.0</span><span class="sxs-lookup"><span data-stu-id="12f58-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="12f58-107">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="12f58-107">Change description</span></span>

<span data-ttu-id="12f58-108">Nas versões anteriores do .NET, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> o não altera o valor da <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> Propriedade na instância de soquete.</span><span class="sxs-lookup"><span data-stu-id="12f58-108">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="12f58-109">A partir do .NET 5,0, quando é <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> concluído com êxito, o valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> é o endereço local do soquete implicitamente ligado.</span><span class="sxs-lookup"><span data-stu-id="12f58-109">Starting in .NET 5.0, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="12f58-110">Esse novo comportamento é consistente com o comportamento de <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> e <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)> / <xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)> .</span><span class="sxs-lookup"><span data-stu-id="12f58-110">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="12f58-111">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="12f58-111">Reason for change</span></span>

<span data-ttu-id="12f58-112">Essa alteração [corrige um bug](https://github.com/dotnet/runtime/issues/915) e torna o comportamento consistente entre `SendTo` variantes.</span><span class="sxs-lookup"><span data-stu-id="12f58-112">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="12f58-113">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="12f58-113">Recommended action</span></span>

<span data-ttu-id="12f58-114">Altere qualquer código que assuma que <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> não alterará o valor de <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="12f58-114">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="12f58-115">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="12f58-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
