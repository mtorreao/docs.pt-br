---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 3dcc1f3b27d93d5641a4bb2d8082aa3fa88882dc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274212"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="0b030-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0b030-102">ChannelPoolSettings</span></span>

<span data-ttu-id="0b030-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="0b030-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b030-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0b030-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0b030-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0b030-105">Methods</span></span>  

 <span data-ttu-id="0b030-106">A classe ChannelPoolSettings não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="0b030-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0b030-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="0b030-107">Properties</span></span>  

 <span data-ttu-id="0b030-108">A classe ChannelPoolSettings tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="0b030-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="0b030-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="0b030-109">IdleTimeout</span></span>  

 <span data-ttu-id="0b030-110">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="0b030-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="0b030-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b030-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b030-112">O tempo máximo que a conexão pode ficar ociosa antes de ser desconectada.</span><span class="sxs-lookup"><span data-stu-id="0b030-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="0b030-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="0b030-113">LeaseTimeout</span></span>  

 <span data-ttu-id="0b030-114">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="0b030-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="0b030-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b030-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b030-116">O tempo máximo para que uma operação de concessão seja concluída antes de atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="0b030-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="0b030-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="0b030-117">MaxOutboundChannelsPerEndpoint</span></span>  

 <span data-ttu-id="0b030-118">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="0b030-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="0b030-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b030-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b030-120">O número máximo de canais de saída para cada ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0b030-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b030-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b030-121">Requirements</span></span>  
  
|<span data-ttu-id="0b030-122">MOF</span><span class="sxs-lookup"><span data-stu-id="0b030-122">MOF</span></span>|<span data-ttu-id="0b030-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="0b030-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0b030-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="0b030-124">Namespace</span></span>|<span data-ttu-id="0b030-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0b030-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b030-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="0b030-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
