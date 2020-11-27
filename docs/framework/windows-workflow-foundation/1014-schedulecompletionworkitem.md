---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275551"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="8f34e-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="8f34e-102">1014 - ScheduleCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="8f34e-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8f34e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f34e-104">ID</span><span class="sxs-lookup"><span data-stu-id="8f34e-104">ID</span></span>|<span data-ttu-id="8f34e-105">1014</span><span class="sxs-lookup"><span data-stu-id="8f34e-105">1014</span></span>|  
|<span data-ttu-id="8f34e-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="8f34e-106">Keywords</span></span>|<span data-ttu-id="8f34e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8f34e-107">WFRuntime</span></span>|  
|<span data-ttu-id="8f34e-108">Nível</span><span class="sxs-lookup"><span data-stu-id="8f34e-108">Level</span></span>|<span data-ttu-id="8f34e-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="8f34e-109">Verbose</span></span>|  
|<span data-ttu-id="8f34e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8f34e-110">Channel</span></span>|<span data-ttu-id="8f34e-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="8f34e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8f34e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="8f34e-112">Description</span></span>  

 <span data-ttu-id="8f34e-113">Indica que um CompletionWorkItem foi agendada.</span><span class="sxs-lookup"><span data-stu-id="8f34e-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8f34e-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="8f34e-114">Message</span></span>  

 <span data-ttu-id="8f34e-115">Um CompletionWorkItem foi agendado para a atividade pai ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="8f34e-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="8f34e-116">Atividade counting “%4 ", DisplayName: “%5", InstanceId: “%6".</span><span class="sxs-lookup"><span data-stu-id="8f34e-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8f34e-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8f34e-117">Details</span></span>  
  
|<span data-ttu-id="8f34e-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="8f34e-118">Data Item Name</span></span>|<span data-ttu-id="8f34e-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="8f34e-119">Data Item Type</span></span>|<span data-ttu-id="8f34e-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="8f34e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8f34e-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="8f34e-121">ParentActivity</span></span>|<span data-ttu-id="8f34e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f34e-122">xs:string</span></span>|<span data-ttu-id="8f34e-123">O nome do tipo de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="8f34e-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="8f34e-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="8f34e-124">ParentDisplayName</span></span>|<span data-ttu-id="8f34e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f34e-125">xs:string</span></span>|<span data-ttu-id="8f34e-126">O nome para exibição de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="8f34e-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="8f34e-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="8f34e-127">ParentInstanceId</span></span>|<span data-ttu-id="8f34e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f34e-128">xs:string</span></span>|<span data-ttu-id="8f34e-129">A identificação de instância de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="8f34e-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="8f34e-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="8f34e-130">CompletedActivity</span></span>|<span data-ttu-id="8f34e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f34e-131">xs:string</span></span>|<span data-ttu-id="8f34e-132">O nome do tipo de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="8f34e-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="8f34e-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="8f34e-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="8f34e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f34e-134">xs:string</span></span>|<span data-ttu-id="8f34e-135">O nome para exibição de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="8f34e-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="8f34e-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="8f34e-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="8f34e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f34e-137">xs:string</span></span>|<span data-ttu-id="8f34e-138">A identificação de instância de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="8f34e-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="8f34e-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8f34e-139">AppDomain</span></span>|<span data-ttu-id="8f34e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f34e-140">xs:string</span></span>|<span data-ttu-id="8f34e-141">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8f34e-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
