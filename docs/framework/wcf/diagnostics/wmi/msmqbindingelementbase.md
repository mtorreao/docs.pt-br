---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 48d26bfa9074fd605e3545579f0bdc2744dfc7d8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267852"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="37bd8-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="37bd8-102">MsmqBindingElementBase</span></span>

<span data-ttu-id="37bd8-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="37bd8-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37bd8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="37bd8-104">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="37bd8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="37bd8-105">Methods</span></span>  

 <span data-ttu-id="37bd8-106">A classe MsmqBindingElementBase não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="37bd8-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="37bd8-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="37bd8-107">Properties</span></span>  

 <span data-ttu-id="37bd8-108">A classe MsmqBindingElementBase tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="37bd8-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="37bd8-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="37bd8-109">CustomDeadLetterQueue</span></span>  

 <span data-ttu-id="37bd8-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="37bd8-110">Data type: string</span></span>  
  
 <span data-ttu-id="37bd8-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-112">Um URI que contém o local da fila de mensagens mortas para cada aplicativo, onde as mensagens que expiraram ou que têm a transferência ou entrega com falha são colocadas.</span><span class="sxs-lookup"><span data-stu-id="37bd8-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="37bd8-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="37bd8-113">DeadLetterQueue</span></span>  

 <span data-ttu-id="37bd8-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="37bd8-114">Data type: string</span></span>  
  
 <span data-ttu-id="37bd8-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-116">Um valor de enumeração que indica o tipo de fila de mensagens mortas a ser usado.</span><span class="sxs-lookup"><span data-stu-id="37bd8-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="37bd8-117">Durável</span><span class="sxs-lookup"><span data-stu-id="37bd8-117">Durable</span></span>  

 <span data-ttu-id="37bd8-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="37bd8-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="37bd8-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-120">Um valor que indica se as mensagens processadas por essa associação são duráveis ou voláteis.</span><span class="sxs-lookup"><span data-stu-id="37bd8-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="37bd8-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="37bd8-121">ExactlyOnce</span></span>  

 <span data-ttu-id="37bd8-122">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="37bd8-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="37bd8-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-124">Um valor booliano que indica se as mensagens processadas por essa associação são recebidas exatamente uma vez.</span><span class="sxs-lookup"><span data-stu-id="37bd8-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="37bd8-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="37bd8-125">MaxRetryCycles</span></span>  

 <span data-ttu-id="37bd8-126">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="37bd8-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="37bd8-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-128">O número máximo de ciclos de repetição para tentar a entrega de mensagens para o aplicativo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="37bd8-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="37bd8-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="37bd8-129">ReceiveErrorHandling</span></span>  

 <span data-ttu-id="37bd8-130">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="37bd8-130">Data type: string</span></span>  
  
 <span data-ttu-id="37bd8-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-132">As configurações de manipulação de mensagens suspeitas.</span><span class="sxs-lookup"><span data-stu-id="37bd8-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="37bd8-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="37bd8-133">ReceiveRetryCount</span></span>  

 <span data-ttu-id="37bd8-134">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="37bd8-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="37bd8-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-136">O número máximo de tentativas de repetição imediatas em uma mensagem que é lida da fila do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="37bd8-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="37bd8-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="37bd8-137">RetryCycleDelay</span></span>  

 <span data-ttu-id="37bd8-138">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="37bd8-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="37bd8-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-140">Um valor que indica o tempo de espera entre os ciclos de repetição ao tentar entregar uma mensagem que não pôde ser entregue imediatamente.</span><span class="sxs-lookup"><span data-stu-id="37bd8-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="37bd8-141">timeToLive</span><span class="sxs-lookup"><span data-stu-id="37bd8-141">TimeToLive</span></span>  

 <span data-ttu-id="37bd8-142">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="37bd8-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="37bd8-143">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-144">O intervalo de tempo que indica por quanto tempo as mensagens processadas por essa associação podem estar na fila antes de expirarem.</span><span class="sxs-lookup"><span data-stu-id="37bd8-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="37bd8-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="37bd8-145">UseMsmqTracing</span></span>  

 <span data-ttu-id="37bd8-146">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="37bd8-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="37bd8-147">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-148">Um valor booliano que indica se as mensagens processadas por essa associação devem ser rastreadas.</span><span class="sxs-lookup"><span data-stu-id="37bd8-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="37bd8-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="37bd8-149">UseSourceJournal</span></span>  

 <span data-ttu-id="37bd8-150">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="37bd8-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="37bd8-151">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="37bd8-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37bd8-152">Um valor booliano que indica se cópias de mensagens processadas por essa associação devem ser armazenadas na fila do diário de origem.</span><span class="sxs-lookup"><span data-stu-id="37bd8-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37bd8-153">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37bd8-153">Requirements</span></span>  
  
|<span data-ttu-id="37bd8-154">MOF</span><span class="sxs-lookup"><span data-stu-id="37bd8-154">MOF</span></span>|<span data-ttu-id="37bd8-155">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="37bd8-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="37bd8-156">Namespace</span><span class="sxs-lookup"><span data-stu-id="37bd8-156">Namespace</span></span>|<span data-ttu-id="37bd8-157">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="37bd8-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37bd8-158">Confira também</span><span class="sxs-lookup"><span data-stu-id="37bd8-158">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
