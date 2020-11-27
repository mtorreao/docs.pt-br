---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: 42ed23654622e29df8ffc210c8d5ba572fa69fd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275343"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="668e4-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="668e4-102">1021 - ScheduleBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="668e4-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="668e4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="668e4-104">ID</span><span class="sxs-lookup"><span data-stu-id="668e4-104">ID</span></span>|<span data-ttu-id="668e4-105">1021</span><span class="sxs-lookup"><span data-stu-id="668e4-105">1021</span></span>|  
|<span data-ttu-id="668e4-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="668e4-106">Keywords</span></span>|<span data-ttu-id="668e4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="668e4-107">WFRuntime</span></span>|  
|<span data-ttu-id="668e4-108">Nível</span><span class="sxs-lookup"><span data-stu-id="668e4-108">Level</span></span>|<span data-ttu-id="668e4-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="668e4-109">Verbose</span></span>|  
|<span data-ttu-id="668e4-110">Canal</span><span class="sxs-lookup"><span data-stu-id="668e4-110">Channel</span></span>|<span data-ttu-id="668e4-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="668e4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="668e4-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="668e4-112">Description</span></span>  

 <span data-ttu-id="668e4-113">Indica que um BookmarkWorkItem foi agendada.</span><span class="sxs-lookup"><span data-stu-id="668e4-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="668e4-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="668e4-114">Message</span></span>  

 <span data-ttu-id="668e4-115">Um BookmarkWorkItem foi agendado para a atividade ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="668e4-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="668e4-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="668e4-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="668e4-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="668e4-117">Details</span></span>  
  
|<span data-ttu-id="668e4-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="668e4-118">Data Item Name</span></span>|<span data-ttu-id="668e4-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="668e4-119">Data Item Type</span></span>|<span data-ttu-id="668e4-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="668e4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="668e4-121">Atividade</span><span class="sxs-lookup"><span data-stu-id="668e4-121">Activity</span></span>|<span data-ttu-id="668e4-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="668e4-122">xs:string</span></span>|<span data-ttu-id="668e4-123">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="668e4-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="668e4-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="668e4-124">DisplayName</span></span>|<span data-ttu-id="668e4-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="668e4-125">xs:string</span></span>|<span data-ttu-id="668e4-126">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="668e4-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="668e4-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="668e4-127">InstanceId</span></span>|<span data-ttu-id="668e4-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="668e4-128">xs:string</span></span>|<span data-ttu-id="668e4-129">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="668e4-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="668e4-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="668e4-130">BookmarkName</span></span>|<span data-ttu-id="668e4-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="668e4-131">xs:string</span></span>|<span data-ttu-id="668e4-132">O nome do indicador.</span><span class="sxs-lookup"><span data-stu-id="668e4-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="668e4-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="668e4-133">BookmarkScope</span></span>|<span data-ttu-id="668e4-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="668e4-134">xs:string</span></span>|<span data-ttu-id="668e4-135">O escopo do indexador.</span><span class="sxs-lookup"><span data-stu-id="668e4-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="668e4-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="668e4-136">AppDomain</span></span>|<span data-ttu-id="668e4-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="668e4-137">xs:string</span></span>|<span data-ttu-id="668e4-138">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="668e4-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
