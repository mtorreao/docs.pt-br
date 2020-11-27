---
title: Ponto de extremidade
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: ceb4e4b41502b00d7bb21f1ecbd8249fccf1ce3b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288808"
---
# <a name="endpoint"></a><span data-ttu-id="12c9b-102">Ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="12c9b-102">Endpoint</span></span>

<span data-ttu-id="12c9b-103">Ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="12c9b-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12c9b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="12c9b-104">Syntax</span></span>  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="12c9b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="12c9b-105">Methods</span></span>  

 <span data-ttu-id="12c9b-106">A classe Endpoint define o método a seguir.</span><span class="sxs-lookup"><span data-stu-id="12c9b-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="12c9b-107">Método</span><span class="sxs-lookup"><span data-stu-id="12c9b-107">Method</span></span>|<span data-ttu-id="12c9b-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="12c9b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12c9b-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="12c9b-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="12c9b-110">Recupera o nome da instância do contador de desempenho da operação</span><span class="sxs-lookup"><span data-stu-id="12c9b-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="12c9b-111">Propriedades</span><span class="sxs-lookup"><span data-stu-id="12c9b-111">Properties</span></span>  

 <span data-ttu-id="12c9b-112">A classe de ponto de extremidade tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="12c9b-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="12c9b-113">Endereço</span><span class="sxs-lookup"><span data-stu-id="12c9b-113">Address</span></span>  

 <span data-ttu-id="12c9b-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="12c9b-114">Data type: string</span></span>  
  
 <span data-ttu-id="12c9b-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-116">Um URI que contém o endereço do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="12c9b-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="12c9b-117">AddressHeaders</span></span>  

 <span data-ttu-id="12c9b-118">Tipo de dados: matriz de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="12c9b-118">Data type: string array</span></span>  
  
 <span data-ttu-id="12c9b-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-120">A coleção de cabeçalhos de endereço anexado a este ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="12c9b-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="12c9b-121">AddressIdentity</span></span>  

 <span data-ttu-id="12c9b-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="12c9b-122">Data type: string</span></span>  
  
 <span data-ttu-id="12c9b-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-124">A identidade do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="12c9b-125">AppDomainid</span><span class="sxs-lookup"><span data-stu-id="12c9b-125">AppDomainId</span></span>  

 <span data-ttu-id="12c9b-126">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="12c9b-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="12c9b-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-128">A ID de AppDomain do AppDomain que hospeda o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="12c9b-129">Comportamentos</span><span class="sxs-lookup"><span data-stu-id="12c9b-129">Behaviors</span></span>  

 <span data-ttu-id="12c9b-130">Tipo de dados: matriz de comportamento</span><span class="sxs-lookup"><span data-stu-id="12c9b-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="12c9b-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-132">A coleção de comportamentos implementados por esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="12c9b-133">Associação</span><span class="sxs-lookup"><span data-stu-id="12c9b-133">Binding</span></span>  

 <span data-ttu-id="12c9b-134">Tipo de dados: Associação</span><span class="sxs-lookup"><span data-stu-id="12c9b-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="12c9b-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-136">A associação usada por esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="12c9b-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="12c9b-137">ContractName</span></span>  

 <span data-ttu-id="12c9b-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="12c9b-138">Data type: string</span></span>  
  
 <span data-ttu-id="12c9b-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-140">Uma cadeia de caracteres que especifica qual contrato esse ponto de extremidade está expondo.</span><span class="sxs-lookup"><span data-stu-id="12c9b-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="12c9b-141">Monoinstancename</span><span class="sxs-lookup"><span data-stu-id="12c9b-141">CounterInstanceName</span></span>  

 <span data-ttu-id="12c9b-142">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="12c9b-142">Data type: string</span></span>  
  
 <span data-ttu-id="12c9b-143">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-144">O nome da instância de contadores de desempenho do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="12c9b-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="12c9b-145">ListenUri</span></span>  

 <span data-ttu-id="12c9b-146">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="12c9b-146">Data type: string</span></span>  
  
 <span data-ttu-id="12c9b-147">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-148">O URI no qual o ponto de extremidade escuta.</span><span class="sxs-lookup"><span data-stu-id="12c9b-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="12c9b-149">Nome</span><span class="sxs-lookup"><span data-stu-id="12c9b-149">Name</span></span>  

 <span data-ttu-id="12c9b-150">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="12c9b-150">Data type: string</span></span>  
  
 <span data-ttu-id="12c9b-151">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-152">O nome exclusivo deste ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="12c9b-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="12c9b-153">ProcessId</span></span>  

 <span data-ttu-id="12c9b-154">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="12c9b-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="12c9b-155">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-156">A ID do processo do processo que hospeda o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="12c9b-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="12c9b-157">ref</span><span class="sxs-lookup"><span data-stu-id="12c9b-157">ref</span></span>  

 <span data-ttu-id="12c9b-158">Tipo de dados: contrato</span><span class="sxs-lookup"><span data-stu-id="12c9b-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="12c9b-159">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c9b-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12c9b-160">O contrato que esse ponto de extremidade está expondo.</span><span class="sxs-lookup"><span data-stu-id="12c9b-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12c9b-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12c9b-161">Requirements</span></span>  
  
|<span data-ttu-id="12c9b-162">MOF</span><span class="sxs-lookup"><span data-stu-id="12c9b-162">MOF</span></span>|<span data-ttu-id="12c9b-163">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="12c9b-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="12c9b-164">Namespace</span><span class="sxs-lookup"><span data-stu-id="12c9b-164">Namespace</span></span>|<span data-ttu-id="12c9b-165">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="12c9b-165">Defined in root\ServiceModel</span></span>|
