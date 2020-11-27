---
title: Contrato
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 0df39bbd0b273f1e898ccbe585be288cc245b7f5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274134"
---
# <a name="contract"></a><span data-ttu-id="82b8a-102">Contrato</span><span class="sxs-lookup"><span data-stu-id="82b8a-102">Contract</span></span>

<span data-ttu-id="82b8a-103">Contrato</span><span class="sxs-lookup"><span data-stu-id="82b8a-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82b8a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="82b8a-104">Syntax</span></span>  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="82b8a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="82b8a-105">Methods</span></span>  

 <span data-ttu-id="82b8a-106">A classe Contract não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="82b8a-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="82b8a-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="82b8a-107">Properties</span></span>  

 <span data-ttu-id="82b8a-108">A classe Contract tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="82b8a-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="82b8a-109">AppDomainid</span><span class="sxs-lookup"><span data-stu-id="82b8a-109">AppDomainId</span></span>  

 <span data-ttu-id="82b8a-110">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="82b8a-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="82b8a-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-112">A ID de AppDomain do AppDomain que hospeda o contrato.</span><span class="sxs-lookup"><span data-stu-id="82b8a-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="82b8a-113">Comportamentos</span><span class="sxs-lookup"><span data-stu-id="82b8a-113">Behaviors</span></span>  

 <span data-ttu-id="82b8a-114">Tipo de dados: matriz de comportamento</span><span class="sxs-lookup"><span data-stu-id="82b8a-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="82b8a-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-116">Os comportamentos associados a este contrato.</span><span class="sxs-lookup"><span data-stu-id="82b8a-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="82b8a-117">Nome</span><span class="sxs-lookup"><span data-stu-id="82b8a-117">Name</span></span>  

 <span data-ttu-id="82b8a-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="82b8a-118">Data type: string</span></span>  
  
 <span data-ttu-id="82b8a-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-120">O nome do contrato em WSDL.</span><span class="sxs-lookup"><span data-stu-id="82b8a-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="82b8a-121">Namespace</span><span class="sxs-lookup"><span data-stu-id="82b8a-121">Namespace</span></span>  

 <span data-ttu-id="82b8a-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="82b8a-122">Data type: string</span></span>  
  
 <span data-ttu-id="82b8a-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-124">O namespace do `portType` elemento no WSDL.</span><span class="sxs-lookup"><span data-stu-id="82b8a-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="82b8a-125">Operações</span><span class="sxs-lookup"><span data-stu-id="82b8a-125">Operations</span></span>  

 <span data-ttu-id="82b8a-126">Tipo de dados: matriz de operação</span><span class="sxs-lookup"><span data-stu-id="82b8a-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="82b8a-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-128">As operações deste contrato.</span><span class="sxs-lookup"><span data-stu-id="82b8a-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="82b8a-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="82b8a-129">ProcessId</span></span>  

 <span data-ttu-id="82b8a-130">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="82b8a-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="82b8a-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-132">A ID do processo que hospeda o contrato.</span><span class="sxs-lookup"><span data-stu-id="82b8a-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="82b8a-133">ref</span><span class="sxs-lookup"><span data-stu-id="82b8a-133">ref</span></span>  

 <span data-ttu-id="82b8a-134">Tipo de dados: contrato</span><span class="sxs-lookup"><span data-stu-id="82b8a-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="82b8a-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-136">O tipo de retorno de chamada quando o contrato é um contrato duplex.</span><span class="sxs-lookup"><span data-stu-id="82b8a-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="82b8a-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="82b8a-137">SessionMode</span></span>  

 <span data-ttu-id="82b8a-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="82b8a-138">Data type: string</span></span>  
  
 <span data-ttu-id="82b8a-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-140">Indica se o contrato requer que a associação associada a este contrato use sessões de canal.</span><span class="sxs-lookup"><span data-stu-id="82b8a-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="82b8a-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="82b8a-141">Type</span></span>  

 <span data-ttu-id="82b8a-142">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="82b8a-142">Data type: string</span></span>  
  
 <span data-ttu-id="82b8a-143">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="82b8a-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82b8a-144">O tipo do contrato.</span><span class="sxs-lookup"><span data-stu-id="82b8a-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82b8a-145">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82b8a-145">Requirements</span></span>  
  
|<span data-ttu-id="82b8a-146">MOF</span><span class="sxs-lookup"><span data-stu-id="82b8a-146">MOF</span></span>|<span data-ttu-id="82b8a-147">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="82b8a-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="82b8a-148">Namespace</span><span class="sxs-lookup"><span data-stu-id="82b8a-148">Namespace</span></span>|<span data-ttu-id="82b8a-149">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="82b8a-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82b8a-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="82b8a-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
