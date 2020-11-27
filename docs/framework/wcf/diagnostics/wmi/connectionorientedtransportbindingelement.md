---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 3c69b73cc05a56a7556630de0f83675590442293
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274147"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="0b295-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0b295-102">ConnectionOrientedTransportBindingElement</span></span>

<span data-ttu-id="0b295-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0b295-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b295-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0b295-104">Syntax</span></span>  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0b295-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0b295-105">Methods</span></span>  

 <span data-ttu-id="0b295-106">A classe ConnectionOrientedTransportBindingElement não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="0b295-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0b295-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="0b295-107">Properties</span></span>  

 <span data-ttu-id="0b295-108">A classe ConnectionOrientedTransportBindingElement tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="0b295-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="0b295-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="0b295-109">ChannelInitializationTimeout</span></span>  

 <span data-ttu-id="0b295-110">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="0b295-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="0b295-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b295-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b295-112">O TimeSpan que especifica por quanto tempo a inicialização do canal deve ser concluída antes de atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="0b295-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="0b295-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="0b295-113">ConnectionBufferSize</span></span>  

 <span data-ttu-id="0b295-114">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="0b295-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="0b295-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b295-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b295-116">O tamanho do buffer usado para transmitir uma parte da mensagem serializada na conexão do cliente ou serviço.</span><span class="sxs-lookup"><span data-stu-id="0b295-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="0b295-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="0b295-117">HostNameComparisonMode</span></span>  

 <span data-ttu-id="0b295-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="0b295-118">Data type: string</span></span>  
  
 <span data-ttu-id="0b295-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b295-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b295-120">Um valor que indica se o nome do host é usado para acessar o serviço ao fazer a correspondência no URI.</span><span class="sxs-lookup"><span data-stu-id="0b295-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="0b295-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="0b295-121">MaxBufferSize</span></span>  

 <span data-ttu-id="0b295-122">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="0b295-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="0b295-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b295-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b295-124">O tamanho máximo do buffer a ser usado.</span><span class="sxs-lookup"><span data-stu-id="0b295-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="0b295-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="0b295-125">MaxOutputDelay</span></span>  

 <span data-ttu-id="0b295-126">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="0b295-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="0b295-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b295-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b295-128">O intervalo máximo de tempo que uma parte de uma mensagem ou uma mensagem completa pode permanecer armazenada em buffer na memória antes de ser enviada.</span><span class="sxs-lookup"><span data-stu-id="0b295-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="0b295-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="0b295-129">MaxPendingAccepts</span></span>  

 <span data-ttu-id="0b295-130">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="0b295-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="0b295-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b295-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b295-132">O número máximo de threads de aceitação assíncrona pendentes que estão disponíveis para processar conexões de entrada no serviço.</span><span class="sxs-lookup"><span data-stu-id="0b295-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="0b295-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="0b295-133">MaxPendingConnections</span></span>  

 <span data-ttu-id="0b295-134">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="0b295-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="0b295-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b295-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b295-136">O número máximo de conexões pendentes.</span><span class="sxs-lookup"><span data-stu-id="0b295-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="0b295-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="0b295-137">TransferMode</span></span>  

 <span data-ttu-id="0b295-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="0b295-138">Data type: string</span></span>  
  
 <span data-ttu-id="0b295-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0b295-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0b295-140">Um valor que especifica se as mensagens são armazenadas em buffer ou transmitidas com o transporte orientado a conexão.</span><span class="sxs-lookup"><span data-stu-id="0b295-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b295-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b295-141">Requirements</span></span>  
  
|<span data-ttu-id="0b295-142">MOF</span><span class="sxs-lookup"><span data-stu-id="0b295-142">MOF</span></span>|<span data-ttu-id="0b295-143">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="0b295-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0b295-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="0b295-144">Namespace</span></span>|<span data-ttu-id="0b295-145">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0b295-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b295-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="0b295-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
