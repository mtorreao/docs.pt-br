---
title: Serviço
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: aa4eecbcc8a2ef818cd99d777b0e3c2f1f222e46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273276"
---
# <a name="service"></a><span data-ttu-id="c33bf-102">Serviço</span><span class="sxs-lookup"><span data-stu-id="c33bf-102">Service</span></span>

<span data-ttu-id="c33bf-103">Serviço</span><span class="sxs-lookup"><span data-stu-id="c33bf-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c33bf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c33bf-104">Syntax</span></span>  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c33bf-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c33bf-105">Methods</span></span>  

 <span data-ttu-id="c33bf-106">A classe de serviço não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="c33bf-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c33bf-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="c33bf-107">Properties</span></span>  

 <span data-ttu-id="c33bf-108">A classe de serviço tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c33bf-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="c33bf-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="c33bf-109">BaseAddresses</span></span>  

 <span data-ttu-id="c33bf-110">Tipo de dados: matriz de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c33bf-110">Data type: string array</span></span>  
  
 <span data-ttu-id="c33bf-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-112">Os endereços base usados pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="c33bf-113">Comportamentos</span><span class="sxs-lookup"><span data-stu-id="c33bf-113">Behaviors</span></span>  

 <span data-ttu-id="c33bf-114">Tipo de dados: matriz de comportamento</span><span class="sxs-lookup"><span data-stu-id="c33bf-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="c33bf-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-116">Os comportamentos associados a esse serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="c33bf-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="c33bf-117">ConfigurationName</span></span>  

 <span data-ttu-id="c33bf-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c33bf-118">Data type: string</span></span>  
  
 <span data-ttu-id="c33bf-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c33bf-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="c33bf-121">Monoinstancename</span><span class="sxs-lookup"><span data-stu-id="c33bf-121">CounterInstanceName</span></span>  

 <span data-ttu-id="c33bf-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c33bf-122">Data type: string</span></span>  
  
 <span data-ttu-id="c33bf-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-124">O nome da instância dos contadores de desempenho do serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="c33bf-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="c33bf-125">DistinguishedName</span></span>  

 <span data-ttu-id="c33bf-126">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c33bf-126">Data type: string</span></span>  
  
 <span data-ttu-id="c33bf-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-128">Nome do serviço no endereço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="c33bf-129">Extensões</span><span class="sxs-lookup"><span data-stu-id="c33bf-129">Extensions</span></span>  

 <span data-ttu-id="c33bf-130">Tipo de dados: matriz de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c33bf-130">Data type: string array</span></span>  
  
 <span data-ttu-id="c33bf-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-132">Os contextos de instância para as extensões da instância de serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="c33bf-133">Metadados</span><span class="sxs-lookup"><span data-stu-id="c33bf-133">Metadata</span></span>  

 <span data-ttu-id="c33bf-134">Tipo de dados: matriz de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c33bf-134">Data type: string array</span></span>  
  
 <span data-ttu-id="c33bf-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-136">As configurações de metadados de serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c33bf-137">Nome</span><span class="sxs-lookup"><span data-stu-id="c33bf-137">Name</span></span>  

 <span data-ttu-id="c33bf-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c33bf-138">Data type: string</span></span>  
  
 <span data-ttu-id="c33bf-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-140">O nome exclusivo deste serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="c33bf-141">Namespace</span><span class="sxs-lookup"><span data-stu-id="c33bf-141">Namespace</span></span>  

 <span data-ttu-id="c33bf-142">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c33bf-142">Data type: string</span></span>  
  
 <span data-ttu-id="c33bf-143">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-144">O namespace do serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="c33bf-145">Aberto</span><span class="sxs-lookup"><span data-stu-id="c33bf-145">Opened</span></span>  

 <span data-ttu-id="c33bf-146">Tipo de dados: DateTime</span><span class="sxs-lookup"><span data-stu-id="c33bf-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="c33bf-147">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-148">A hora em que o serviço foi aberto.</span><span class="sxs-lookup"><span data-stu-id="c33bf-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="c33bf-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="c33bf-149">OutgoingChannels</span></span>  

 <span data-ttu-id="c33bf-150">Tipo de dados: matriz de canal</span><span class="sxs-lookup"><span data-stu-id="c33bf-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="c33bf-151">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-152">Os canais que estão saindo da instância do serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="c33bf-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="c33bf-153">ProcessId</span></span>  

 <span data-ttu-id="c33bf-154">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="c33bf-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="c33bf-155">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c33bf-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c33bf-156">A ID do processo que hospeda o serviço.</span><span class="sxs-lookup"><span data-stu-id="c33bf-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c33bf-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c33bf-157">Requirements</span></span>  
  
|<span data-ttu-id="c33bf-158">MOF</span><span class="sxs-lookup"><span data-stu-id="c33bf-158">MOF</span></span>|<span data-ttu-id="c33bf-159">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="c33bf-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c33bf-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="c33bf-160">Namespace</span></span>|<span data-ttu-id="c33bf-161">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c33bf-161">Defined in root\ServiceModel</span></span>|
