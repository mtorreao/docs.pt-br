---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: c0d8572f192a8faa22327fd671cd9ea49c5054ca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275538"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="6a43d-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="6a43d-102">1015 - StartCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="6a43d-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="6a43d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a43d-104">ID</span><span class="sxs-lookup"><span data-stu-id="6a43d-104">ID</span></span>|<span data-ttu-id="6a43d-105">1015</span><span class="sxs-lookup"><span data-stu-id="6a43d-105">1015</span></span>|  
|<span data-ttu-id="6a43d-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="6a43d-106">Keywords</span></span>|<span data-ttu-id="6a43d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6a43d-107">WFRuntime</span></span>|  
|<span data-ttu-id="6a43d-108">Nível</span><span class="sxs-lookup"><span data-stu-id="6a43d-108">Level</span></span>|<span data-ttu-id="6a43d-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="6a43d-109">Verbose</span></span>|  
|<span data-ttu-id="6a43d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6a43d-110">Channel</span></span>|<span data-ttu-id="6a43d-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="6a43d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6a43d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="6a43d-112">Description</span></span>  

 <span data-ttu-id="6a43d-113">Indica que um CompletionWorkItem está sendo a execução.</span><span class="sxs-lookup"><span data-stu-id="6a43d-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6a43d-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="6a43d-114">Message</span></span>  

 <span data-ttu-id="6a43d-115">Iniciar a execução de um CompletionWorkItem para atividades pai “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="6a43d-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="6a43d-116">Atividade counting “%4 ", DisplayName: “%5", InstanceId: “%6".</span><span class="sxs-lookup"><span data-stu-id="6a43d-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6a43d-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="6a43d-117">Details</span></span>  
  
|<span data-ttu-id="6a43d-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="6a43d-118">Data Item Name</span></span>|<span data-ttu-id="6a43d-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="6a43d-119">Data Item Type</span></span>|<span data-ttu-id="6a43d-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="6a43d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6a43d-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="6a43d-121">ParentActivity</span></span>|<span data-ttu-id="6a43d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a43d-122">xs:string</span></span>|<span data-ttu-id="6a43d-123">O nome do tipo de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="6a43d-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="6a43d-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="6a43d-124">ParentDisplayName</span></span>|<span data-ttu-id="6a43d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a43d-125">xs:string</span></span>|<span data-ttu-id="6a43d-126">O nome para exibição de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="6a43d-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="6a43d-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="6a43d-127">ParentInstanceId</span></span>|<span data-ttu-id="6a43d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a43d-128">xs:string</span></span>|<span data-ttu-id="6a43d-129">A identificação de instância de atividade pai.</span><span class="sxs-lookup"><span data-stu-id="6a43d-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="6a43d-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="6a43d-130">CompletedActivity</span></span>|<span data-ttu-id="6a43d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a43d-131">xs:string</span></span>|<span data-ttu-id="6a43d-132">O nome do tipo de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="6a43d-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="6a43d-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6a43d-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="6a43d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a43d-134">xs:string</span></span>|<span data-ttu-id="6a43d-135">O nome para exibição de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="6a43d-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="6a43d-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6a43d-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="6a43d-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a43d-137">xs:string</span></span>|<span data-ttu-id="6a43d-138">A identificação de instância de atividade concluída.</span><span class="sxs-lookup"><span data-stu-id="6a43d-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="6a43d-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6a43d-139">AppDomain</span></span>|<span data-ttu-id="6a43d-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a43d-140">xs:string</span></span>|<span data-ttu-id="6a43d-141">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6a43d-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
