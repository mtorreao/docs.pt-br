---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: 557155fab35a37bdbaa45efb26d6bc025ad825c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281827"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="abf36-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="abf36-102">1031 - CompleteFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="abf36-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="abf36-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="abf36-104">ID</span><span class="sxs-lookup"><span data-stu-id="abf36-104">ID</span></span>|<span data-ttu-id="abf36-105">1031</span><span class="sxs-lookup"><span data-stu-id="abf36-105">1031</span></span>|  
|<span data-ttu-id="abf36-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="abf36-106">Keywords</span></span>|<span data-ttu-id="abf36-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="abf36-107">WFRuntime</span></span>|  
|<span data-ttu-id="abf36-108">Nível</span><span class="sxs-lookup"><span data-stu-id="abf36-108">Level</span></span>|<span data-ttu-id="abf36-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="abf36-109">Verbose</span></span>|  
|<span data-ttu-id="abf36-110">Canal</span><span class="sxs-lookup"><span data-stu-id="abf36-110">Channel</span></span>|<span data-ttu-id="abf36-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="abf36-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="abf36-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="abf36-112">Description</span></span>  

 <span data-ttu-id="abf36-113">Indica que um FaultWorkItem terminado.</span><span class="sxs-lookup"><span data-stu-id="abf36-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="abf36-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="abf36-114">Message</span></span>  

 <span data-ttu-id="abf36-115">Um FaultWorkItem concluiu para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="abf36-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="abf36-116">A exceção é propagada de atividade “%4 ", DisplayName: “%5", InstanceId: “%6".</span><span class="sxs-lookup"><span data-stu-id="abf36-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="abf36-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="abf36-117">Details</span></span>  
  
|<span data-ttu-id="abf36-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="abf36-118">Data Item Name</span></span>|<span data-ttu-id="abf36-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="abf36-119">Data Item Type</span></span>|<span data-ttu-id="abf36-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="abf36-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="abf36-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="abf36-121">FaultActivity</span></span>|<span data-ttu-id="abf36-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="abf36-122">xs:string</span></span>|<span data-ttu-id="abf36-123">O nome do tipo de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="abf36-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="abf36-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="abf36-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="abf36-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="abf36-125">xs:string</span></span>|<span data-ttu-id="abf36-126">O nome para exibição de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="abf36-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="abf36-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="abf36-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="abf36-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="abf36-128">xs:string</span></span>|<span data-ttu-id="abf36-129">A identificação de instância de atividade de falha.</span><span class="sxs-lookup"><span data-stu-id="abf36-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="abf36-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="abf36-130">ExceptionActivity</span></span>|<span data-ttu-id="abf36-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="abf36-131">xs:string</span></span>|<span data-ttu-id="abf36-132">O nome do tipo de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="abf36-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="abf36-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="abf36-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="abf36-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="abf36-134">xs:string</span></span>|<span data-ttu-id="abf36-135">O nome para exibição de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="abf36-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="abf36-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="abf36-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="abf36-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="abf36-137">xs:string</span></span>|<span data-ttu-id="abf36-138">A identificação de instância de atividade que apresentou a exceção.</span><span class="sxs-lookup"><span data-stu-id="abf36-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="abf36-139">Exceção</span><span class="sxs-lookup"><span data-stu-id="abf36-139">Exception</span></span>|<span data-ttu-id="abf36-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="abf36-140">xs:string</span></span>|<span data-ttu-id="abf36-141">Os detalhes de exceção para a exceção</span><span class="sxs-lookup"><span data-stu-id="abf36-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="abf36-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="abf36-142">AppDomain</span></span>|<span data-ttu-id="abf36-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="abf36-143">xs:string</span></span>|<span data-ttu-id="abf36-144">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="abf36-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
