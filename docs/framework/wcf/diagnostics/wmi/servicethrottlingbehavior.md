---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 3bcf205964a22cdb418d0158e5ee6439169538ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273978"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="19b72-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="19b72-102">ServiceThrottlingBehavior</span></span>

<span data-ttu-id="19b72-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="19b72-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19b72-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="19b72-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="19b72-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="19b72-105">Methods</span></span>  

 <span data-ttu-id="19b72-106">A classe ServiceThrottlingBehavior não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="19b72-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="19b72-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="19b72-107">Properties</span></span>  

 <span data-ttu-id="19b72-108">A classe ServiceThrottlingBehavior tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="19b72-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="19b72-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="19b72-109">MaxConcurrentCalls</span></span>  

 <span data-ttu-id="19b72-110">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="19b72-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="19b72-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19b72-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b72-112">O número máximo de mensagens processando ativamente em todos os objetos do Dispatcher em um ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="19b72-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="19b72-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="19b72-113">MaxConcurrentInstances</span></span>  

 <span data-ttu-id="19b72-114">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="19b72-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="19b72-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19b72-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b72-116">O número máximo de objetos de serviço que podem ser executados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="19b72-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="19b72-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="19b72-117">MaxConcurrentSessions</span></span>  

 <span data-ttu-id="19b72-118">Tipo de dados: sint32</span><span class="sxs-lookup"><span data-stu-id="19b72-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="19b72-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19b72-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19b72-120">O número máximo de sessões que um host pode aceitar ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="19b72-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19b72-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19b72-121">Requirements</span></span>  
  
|<span data-ttu-id="19b72-122">MOF</span><span class="sxs-lookup"><span data-stu-id="19b72-122">MOF</span></span>|<span data-ttu-id="19b72-123">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="19b72-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="19b72-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="19b72-124">Namespace</span></span>|<span data-ttu-id="19b72-125">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="19b72-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19b72-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="19b72-126">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
