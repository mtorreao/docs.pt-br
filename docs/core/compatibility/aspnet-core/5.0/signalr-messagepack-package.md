---
title: 'Alteração significativa: Signalr: protocolo Hub MessagePack movido para o pacote MessagePack 2. x'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core o Signaler 5,0 intitulado: protocolo Hub MessagePack movido para o pacote MessagePack 2. x'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1e666c40d7046233c9fb06af819b901fd1251b06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760529"
---
# <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="b6808-103">Signalr: protocolo Hub MessagePack movido para o pacote MessagePack 2. x</span><span class="sxs-lookup"><span data-stu-id="b6808-103">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="b6808-104">O protocolo ASP.NET Core de [Hub MessagePack](/aspnet/core/signalr/messagepackhubprotocol) signalr não usa o [pacote NuGet MessagePack](https://www.nuget.org/packages/MessagePack) para serialização MessagePack.</span><span class="sxs-lookup"><span data-stu-id="b6808-104">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="b6808-105">ASP.NET Core 5,0 atualiza o pacote de 1. x para a versão mais recente do pacote 2. x.</span><span class="sxs-lookup"><span data-stu-id="b6808-105">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="b6808-106">Para obter uma discussão sobre esse problema, consulte [dotnet/aspnetcore # 18692](https://github.com/dotnet/aspnetcore/issues/18692).</span><span class="sxs-lookup"><span data-stu-id="b6808-106">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b6808-107">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="b6808-107">Version introduced</span></span>

<span data-ttu-id="b6808-108">5,0 visualização 1</span><span class="sxs-lookup"><span data-stu-id="b6808-108">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="b6808-109">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="b6808-109">Old behavior</span></span>

<span data-ttu-id="b6808-110">ASP.NET Core Signalr usou o pacote MessagePack 1. x para serializar e desserializar mensagens MessagePack.</span><span class="sxs-lookup"><span data-stu-id="b6808-110">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="b6808-111">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="b6808-111">New behavior</span></span>

<span data-ttu-id="b6808-112">ASP.NET Core Signalr usa o pacote MessagePack 2. x para serializar e desserializar mensagens MessagePack.</span><span class="sxs-lookup"><span data-stu-id="b6808-112">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b6808-113">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="b6808-113">Reason for change</span></span>

<span data-ttu-id="b6808-114">As melhorias mais recentes no pacote MessagePack 2. x adicionam uma funcionalidade útil.</span><span class="sxs-lookup"><span data-stu-id="b6808-114">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b6808-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="b6808-115">Recommended action</span></span>

<span data-ttu-id="b6808-116">Essa alteração significativa se aplica quando:</span><span class="sxs-lookup"><span data-stu-id="b6808-116">This breaking change applies when:</span></span>

* <span data-ttu-id="b6808-117">Definindo ou Configurando valores em <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> .</span><span class="sxs-lookup"><span data-stu-id="b6808-117">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="b6808-118">Usar as APIs do MessagePack diretamente e usar o protocolo Hub MessagePack do ASP.NET Core Signalr no mesmo projeto.</span><span class="sxs-lookup"><span data-stu-id="b6808-118">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="b6808-119">A versão mais recente será carregada em vez da versão anterior.</span><span class="sxs-lookup"><span data-stu-id="b6808-119">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="b6808-120">Para obter diretrizes de migração dos autores de pacotes, consulte [migrando do MessagePack v1. x para o MessagePack v2. x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span><span class="sxs-lookup"><span data-stu-id="b6808-120">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="b6808-121">Alguns aspectos da serialização e desserialização de mensagens são afetados.</span><span class="sxs-lookup"><span data-stu-id="b6808-121">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="b6808-122">Especificamente, há [alterações comportamentais em como os valores de data e hora são serializados](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span><span class="sxs-lookup"><span data-stu-id="b6808-122">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b6808-123">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="b6808-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
