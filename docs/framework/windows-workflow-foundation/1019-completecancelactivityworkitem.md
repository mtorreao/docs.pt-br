---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 903b497fb3f244fd40c6888829ef71dddd455251
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275473"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="92f3d-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="92f3d-102">1019 - CompleteCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="92f3d-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="92f3d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="92f3d-104">ID</span><span class="sxs-lookup"><span data-stu-id="92f3d-104">ID</span></span>|<span data-ttu-id="92f3d-105">1019</span><span class="sxs-lookup"><span data-stu-id="92f3d-105">1019</span></span>|  
|<span data-ttu-id="92f3d-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="92f3d-106">Keywords</span></span>|<span data-ttu-id="92f3d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="92f3d-107">WFRuntime</span></span>|  
|<span data-ttu-id="92f3d-108">Nível</span><span class="sxs-lookup"><span data-stu-id="92f3d-108">Level</span></span>|<span data-ttu-id="92f3d-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="92f3d-109">Verbose</span></span>|  
|<span data-ttu-id="92f3d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="92f3d-110">Channel</span></span>|<span data-ttu-id="92f3d-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="92f3d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="92f3d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="92f3d-112">Description</span></span>  

 <span data-ttu-id="92f3d-113">Indica que um CancelActivityWorkItem terminado.</span><span class="sxs-lookup"><span data-stu-id="92f3d-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="92f3d-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="92f3d-114">Message</span></span>  

 <span data-ttu-id="92f3d-115">Um CancelActivityWorkItem concluiu para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="92f3d-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="92f3d-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="92f3d-116">Details</span></span>  
  
|<span data-ttu-id="92f3d-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="92f3d-117">Data Item Name</span></span>|<span data-ttu-id="92f3d-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="92f3d-118">Data Item Type</span></span>|<span data-ttu-id="92f3d-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="92f3d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="92f3d-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="92f3d-120">Activity</span></span>|<span data-ttu-id="92f3d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="92f3d-121">xs:string</span></span>|<span data-ttu-id="92f3d-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="92f3d-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="92f3d-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="92f3d-123">DisplayName</span></span>|<span data-ttu-id="92f3d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="92f3d-124">xs:string</span></span>|<span data-ttu-id="92f3d-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="92f3d-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="92f3d-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="92f3d-126">InstanceId</span></span>|<span data-ttu-id="92f3d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="92f3d-127">xs:string</span></span>|<span data-ttu-id="92f3d-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="92f3d-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="92f3d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="92f3d-129">AppDomain</span></span>|<span data-ttu-id="92f3d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="92f3d-130">xs:string</span></span>|<span data-ttu-id="92f3d-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="92f3d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
