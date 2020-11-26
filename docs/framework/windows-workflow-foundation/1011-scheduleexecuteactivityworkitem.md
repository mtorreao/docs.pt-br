---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: dc209fc41dc6b076dfb897880f753be51f7fb0ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239686"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="605a9-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="605a9-102">1011 - ScheduleExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="605a9-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="605a9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="605a9-104">ID</span><span class="sxs-lookup"><span data-stu-id="605a9-104">ID</span></span>|<span data-ttu-id="605a9-105">1011</span><span class="sxs-lookup"><span data-stu-id="605a9-105">1011</span></span>|  
|<span data-ttu-id="605a9-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="605a9-106">Keywords</span></span>|<span data-ttu-id="605a9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="605a9-107">WFRuntime</span></span>|  
|<span data-ttu-id="605a9-108">Nível</span><span class="sxs-lookup"><span data-stu-id="605a9-108">Level</span></span>|<span data-ttu-id="605a9-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="605a9-109">Verbose</span></span>|  
|<span data-ttu-id="605a9-110">Canal</span><span class="sxs-lookup"><span data-stu-id="605a9-110">Channel</span></span>|<span data-ttu-id="605a9-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="605a9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="605a9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="605a9-112">Description</span></span>  

 <span data-ttu-id="605a9-113">Indica que um ExecuteActivityWorkItem foi agendada.</span><span class="sxs-lookup"><span data-stu-id="605a9-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="605a9-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="605a9-114">Message</span></span>  

 <span data-ttu-id="605a9-115">Um ExecuteActivityWorkItem foi agendada para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="605a9-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="605a9-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="605a9-116">Details</span></span>  
  
|<span data-ttu-id="605a9-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="605a9-117">Data Item Name</span></span>|<span data-ttu-id="605a9-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="605a9-118">Data Item Type</span></span>|<span data-ttu-id="605a9-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="605a9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="605a9-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="605a9-120">Activity</span></span>|<span data-ttu-id="605a9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="605a9-121">xs:string</span></span>|<span data-ttu-id="605a9-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="605a9-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="605a9-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="605a9-123">DisplayName</span></span>|<span data-ttu-id="605a9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="605a9-124">xs:string</span></span>|<span data-ttu-id="605a9-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="605a9-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="605a9-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="605a9-126">InstanceId</span></span>|<span data-ttu-id="605a9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="605a9-127">xs:string</span></span>|<span data-ttu-id="605a9-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="605a9-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="605a9-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="605a9-129">AppDomain</span></span>|<span data-ttu-id="605a9-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="605a9-130">xs:string</span></span>|<span data-ttu-id="605a9-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="605a9-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
