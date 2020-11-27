---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: da35201f2b3e3bc07e0b9139b0584ce37011e168
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294307"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="e0d27-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="e0d27-102">1032 - ScheduleRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="e0d27-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e0d27-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0d27-104">ID</span><span class="sxs-lookup"><span data-stu-id="e0d27-104">ID</span></span>|<span data-ttu-id="e0d27-105">1032</span><span class="sxs-lookup"><span data-stu-id="e0d27-105">1032</span></span>|  
|<span data-ttu-id="e0d27-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="e0d27-106">Keywords</span></span>|<span data-ttu-id="e0d27-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e0d27-107">WFRuntime</span></span>|  
|<span data-ttu-id="e0d27-108">Nível</span><span class="sxs-lookup"><span data-stu-id="e0d27-108">Level</span></span>|<span data-ttu-id="e0d27-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="e0d27-109">Verbose</span></span>|  
|<span data-ttu-id="e0d27-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e0d27-110">Channel</span></span>|<span data-ttu-id="e0d27-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="e0d27-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0d27-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0d27-112">Description</span></span>  

 <span data-ttu-id="e0d27-113">Indica que um RuntimeWorkItem foi agendada.</span><span class="sxs-lookup"><span data-stu-id="e0d27-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0d27-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="e0d27-114">Message</span></span>  

 <span data-ttu-id="e0d27-115">Um item de trabalho de runtime foi agendada para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="e0d27-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0d27-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e0d27-116">Details</span></span>  
  
|<span data-ttu-id="e0d27-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="e0d27-117">Data Item Name</span></span>|<span data-ttu-id="e0d27-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="e0d27-118">Data Item Type</span></span>|<span data-ttu-id="e0d27-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0d27-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0d27-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="e0d27-120">Activity</span></span>|<span data-ttu-id="e0d27-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0d27-121">xs:string</span></span>|<span data-ttu-id="e0d27-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="e0d27-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e0d27-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e0d27-123">DisplayName</span></span>|<span data-ttu-id="e0d27-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0d27-124">xs:string</span></span>|<span data-ttu-id="e0d27-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="e0d27-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e0d27-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e0d27-126">InstanceId</span></span>|<span data-ttu-id="e0d27-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0d27-127">xs:string</span></span>|<span data-ttu-id="e0d27-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="e0d27-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e0d27-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0d27-129">AppDomain</span></span>|<span data-ttu-id="e0d27-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0d27-130">xs:string</span></span>|<span data-ttu-id="e0d27-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e0d27-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
