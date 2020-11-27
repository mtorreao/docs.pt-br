---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274043"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="87fc9-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="87fc9-102">DeliveryRequirementsAttribute</span></span>

<span data-ttu-id="87fc9-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="87fc9-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87fc9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="87fc9-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="87fc9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="87fc9-105">Methods</span></span>  

 <span data-ttu-id="87fc9-106">A classe DeliveryRequirementsAttribute não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="87fc9-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="87fc9-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="87fc9-107">Properties</span></span>  

 <span data-ttu-id="87fc9-108">A classe DeliveryRequirementsAttribute tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="87fc9-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="87fc9-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="87fc9-109">QueuedDeliveryRequirements</span></span>  

 <span data-ttu-id="87fc9-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="87fc9-110">Data type: string</span></span>  
  
 <span data-ttu-id="87fc9-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="87fc9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87fc9-112">Especifica se a associação de um serviço dá suporte a contratos.</span><span class="sxs-lookup"><span data-stu-id="87fc9-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="87fc9-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="87fc9-113">RequireOrderedDelivery</span></span>  

 <span data-ttu-id="87fc9-114">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="87fc9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="87fc9-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="87fc9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87fc9-116">Especifica se a associação oferece suporte a mensagens ordenadas.</span><span class="sxs-lookup"><span data-stu-id="87fc9-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="87fc9-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="87fc9-117">TargetContract</span></span>  

 <span data-ttu-id="87fc9-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="87fc9-118">Data type: string</span></span>  
  
 <span data-ttu-id="87fc9-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="87fc9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87fc9-120">O contrato ao qual se aplica.</span><span class="sxs-lookup"><span data-stu-id="87fc9-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87fc9-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87fc9-121">Requirements</span></span>  
  
|<span data-ttu-id="87fc9-122">MOF</span><span class="sxs-lookup"><span data-stu-id="87fc9-122">MOF</span></span>|<span data-ttu-id="87fc9-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="87fc9-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="87fc9-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="87fc9-124">Namespace</span></span>|<span data-ttu-id="87fc9-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="87fc9-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87fc9-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="87fc9-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
