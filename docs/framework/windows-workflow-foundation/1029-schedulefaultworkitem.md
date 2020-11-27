---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: 5c109607b2d353d3d4a5a693f29ab66bb76c8398
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275083"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="b9a41-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="b9a41-102">1029 - ScheduleFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="b9a41-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="b9a41-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9a41-104">ID</span><span class="sxs-lookup"><span data-stu-id="b9a41-104">ID</span></span>|<span data-ttu-id="b9a41-105">1029</span><span class="sxs-lookup"><span data-stu-id="b9a41-105">1029</span></span>|  
|<span data-ttu-id="b9a41-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="b9a41-106">Keywords</span></span>|<span data-ttu-id="b9a41-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b9a41-107">WFRuntime</span></span>|  
|<span data-ttu-id="b9a41-108">Nível</span><span class="sxs-lookup"><span data-stu-id="b9a41-108">Level</span></span>|<span data-ttu-id="b9a41-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="b9a41-109">Verbose</span></span>|  
|<span data-ttu-id="b9a41-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b9a41-110">Channel</span></span>|<span data-ttu-id="b9a41-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="b9a41-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b9a41-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b9a41-112">Description</span></span>  

 <span data-ttu-id="b9a41-113">Indica que um FaultWorkItem foi agendada.</span><span class="sxs-lookup"><span data-stu-id="b9a41-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b9a41-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="b9a41-114">Message</span></span>  

 <span data-ttu-id="b9a41-115">Um FaultWorkItem foi agendado para a atividade ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="b9a41-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="b9a41-116">A exceção é propagada de atividade “%4 ", DisplayName: “%5", InstanceId: “%6".</span><span class="sxs-lookup"><span data-stu-id="b9a41-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b9a41-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b9a41-117">Details</span></span>  
  
|<span data-ttu-id="b9a41-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="b9a41-118">Data Item Name</span></span>|<span data-ttu-id="b9a41-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="b9a41-119">Data Item Type</span></span>|<span data-ttu-id="b9a41-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="b9a41-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b9a41-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="b9a41-121">FaultActivity</span></span>|<span data-ttu-id="b9a41-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9a41-122">xs:string</span></span>|<span data-ttu-id="b9a41-123">O nome do tipo de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="b9a41-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="b9a41-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b9a41-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="b9a41-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9a41-125">xs:string</span></span>|<span data-ttu-id="b9a41-126">O nome para exibição de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="b9a41-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="b9a41-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b9a41-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="b9a41-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9a41-128">xs:string</span></span>|<span data-ttu-id="b9a41-129">A identificação de instância de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="b9a41-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="b9a41-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="b9a41-130">ExceptionActivity</span></span>|<span data-ttu-id="b9a41-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9a41-131">xs:string</span></span>|<span data-ttu-id="b9a41-132">O nome do tipo de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="b9a41-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b9a41-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b9a41-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="b9a41-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9a41-134">xs:string</span></span>|<span data-ttu-id="b9a41-135">O nome para exibição de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="b9a41-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b9a41-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b9a41-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="b9a41-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9a41-137">xs:string</span></span>|<span data-ttu-id="b9a41-138">A identificação de instância de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="b9a41-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b9a41-139">Exceção</span><span class="sxs-lookup"><span data-stu-id="b9a41-139">Exception</span></span>|<span data-ttu-id="b9a41-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9a41-140">xs:string</span></span>|<span data-ttu-id="b9a41-141">Os detalhes de exceção para a exceção</span><span class="sxs-lookup"><span data-stu-id="b9a41-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="b9a41-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b9a41-142">AppDomain</span></span>|<span data-ttu-id="b9a41-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="b9a41-143">xs:string</span></span>|<span data-ttu-id="b9a41-144">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b9a41-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
