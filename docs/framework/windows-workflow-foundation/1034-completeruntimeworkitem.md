---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: 837adc9e143060284f2373a049bc9ad9c8cee336
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294281"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="3d68a-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="3d68a-102">1034 - CompleteRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="3d68a-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="3d68a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3d68a-104">ID</span><span class="sxs-lookup"><span data-stu-id="3d68a-104">ID</span></span>|<span data-ttu-id="3d68a-105">1034</span><span class="sxs-lookup"><span data-stu-id="3d68a-105">1034</span></span>|  
|<span data-ttu-id="3d68a-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3d68a-106">Keywords</span></span>|<span data-ttu-id="3d68a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3d68a-107">WFRuntime</span></span>|  
|<span data-ttu-id="3d68a-108">Nível</span><span class="sxs-lookup"><span data-stu-id="3d68a-108">Level</span></span>|<span data-ttu-id="3d68a-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="3d68a-109">Verbose</span></span>|  
|<span data-ttu-id="3d68a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3d68a-110">Channel</span></span>|<span data-ttu-id="3d68a-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="3d68a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3d68a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="3d68a-112">Description</span></span>  

 <span data-ttu-id="3d68a-113">Indica que um RuntimeWorkItem terminado.</span><span class="sxs-lookup"><span data-stu-id="3d68a-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3d68a-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="3d68a-114">Message</span></span>  

 <span data-ttu-id="3d68a-115">Um item de trabalho de runtime concluiu para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="3d68a-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3d68a-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3d68a-116">Details</span></span>  
  
|<span data-ttu-id="3d68a-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="3d68a-117">Data Item Name</span></span>|<span data-ttu-id="3d68a-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="3d68a-118">Data Item Type</span></span>|<span data-ttu-id="3d68a-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="3d68a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3d68a-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="3d68a-120">Activity</span></span>|<span data-ttu-id="3d68a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d68a-121">xs:string</span></span>|<span data-ttu-id="3d68a-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="3d68a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3d68a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3d68a-123">DisplayName</span></span>|<span data-ttu-id="3d68a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d68a-124">xs:string</span></span>|<span data-ttu-id="3d68a-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="3d68a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3d68a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3d68a-126">InstanceId</span></span>|<span data-ttu-id="3d68a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d68a-127">xs:string</span></span>|<span data-ttu-id="3d68a-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="3d68a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3d68a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3d68a-129">AppDomain</span></span>|<span data-ttu-id="3d68a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d68a-130">xs:string</span></span>|<span data-ttu-id="3d68a-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3d68a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
