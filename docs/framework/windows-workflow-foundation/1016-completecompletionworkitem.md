---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: a192ffe19777ca3e2e9784f6506a0c2929ced000
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275525"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="87b5a-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="87b5a-102">1016 - CompleteCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="87b5a-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="87b5a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87b5a-104">ID</span><span class="sxs-lookup"><span data-stu-id="87b5a-104">ID</span></span>|<span data-ttu-id="87b5a-105">1016</span><span class="sxs-lookup"><span data-stu-id="87b5a-105">1016</span></span>|  
|<span data-ttu-id="87b5a-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="87b5a-106">Keywords</span></span>|<span data-ttu-id="87b5a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="87b5a-107">WFRuntime</span></span>|  
|<span data-ttu-id="87b5a-108">Nível</span><span class="sxs-lookup"><span data-stu-id="87b5a-108">Level</span></span>|<span data-ttu-id="87b5a-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="87b5a-109">Verbose</span></span>|  
|<span data-ttu-id="87b5a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="87b5a-110">Channel</span></span>|<span data-ttu-id="87b5a-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="87b5a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="87b5a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="87b5a-112">Description</span></span>  

 <span data-ttu-id="87b5a-113">Indica que um CompletionWorkItem terminado.</span><span class="sxs-lookup"><span data-stu-id="87b5a-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="87b5a-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="87b5a-114">Message</span></span>  

 <span data-ttu-id="87b5a-115">Um CompletionWorkItem concluiu para atividades pai “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="87b5a-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="87b5a-116">Atividade counting “%4 ", DisplayName: “%5", InstanceId: “%6".</span><span class="sxs-lookup"><span data-stu-id="87b5a-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="87b5a-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="87b5a-117">Details</span></span>  
  
|<span data-ttu-id="87b5a-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="87b5a-118">Data Item Name</span></span>|<span data-ttu-id="87b5a-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="87b5a-119">Data Item Type</span></span>|<span data-ttu-id="87b5a-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="87b5a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="87b5a-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="87b5a-121">ParentActivity</span></span>|<span data-ttu-id="87b5a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="87b5a-122">xs:string</span></span>|<span data-ttu-id="87b5a-123">O nome do tipo de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="87b5a-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="87b5a-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="87b5a-124">ParentDisplayName</span></span>|<span data-ttu-id="87b5a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="87b5a-125">xs:string</span></span>|<span data-ttu-id="87b5a-126">O nome para exibição de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="87b5a-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="87b5a-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="87b5a-127">ParentInstanceId</span></span>|<span data-ttu-id="87b5a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="87b5a-128">xs:string</span></span>|<span data-ttu-id="87b5a-129">A identificação de instância de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="87b5a-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="87b5a-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="87b5a-130">CompletedActivity</span></span>|<span data-ttu-id="87b5a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="87b5a-131">xs:string</span></span>|<span data-ttu-id="87b5a-132">O nome do tipo de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="87b5a-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="87b5a-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="87b5a-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="87b5a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="87b5a-134">xs:string</span></span>|<span data-ttu-id="87b5a-135">O nome para exibição de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="87b5a-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="87b5a-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="87b5a-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="87b5a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="87b5a-137">xs:string</span></span>|<span data-ttu-id="87b5a-138">A identificação de instância de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="87b5a-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="87b5a-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="87b5a-139">AppDomain</span></span>|<span data-ttu-id="87b5a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="87b5a-140">xs:string</span></span>|<span data-ttu-id="87b5a-141">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="87b5a-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
