---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: 654f961088c371ab53e4a81f40e3c63335efb1a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239582"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="f7662-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f7662-102">1013 - CompleteExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="f7662-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="f7662-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f7662-104">ID</span><span class="sxs-lookup"><span data-stu-id="f7662-104">ID</span></span>|<span data-ttu-id="f7662-105">1013</span><span class="sxs-lookup"><span data-stu-id="f7662-105">1013</span></span>|  
|<span data-ttu-id="f7662-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="f7662-106">Keywords</span></span>|<span data-ttu-id="f7662-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f7662-107">WFRuntime</span></span>|  
|<span data-ttu-id="f7662-108">Nível</span><span class="sxs-lookup"><span data-stu-id="f7662-108">Level</span></span>|<span data-ttu-id="f7662-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="f7662-109">Verbose</span></span>|  
|<span data-ttu-id="f7662-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f7662-110">Channel</span></span>|<span data-ttu-id="f7662-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="f7662-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f7662-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7662-112">Description</span></span>  

 <span data-ttu-id="f7662-113">Indica que um ExecuteActivityWorkItem concluiu</span><span class="sxs-lookup"><span data-stu-id="f7662-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="f7662-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f7662-114">Message</span></span>  

 <span data-ttu-id="f7662-115">Um ExecuteActivityWorkItem concluiu para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="f7662-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f7662-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f7662-116">Details</span></span>  
  
|<span data-ttu-id="f7662-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="f7662-117">Data Item Name</span></span>|<span data-ttu-id="f7662-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="f7662-118">Data Item Type</span></span>|<span data-ttu-id="f7662-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7662-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f7662-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="f7662-120">Activity</span></span>|<span data-ttu-id="f7662-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7662-121">xs:string</span></span>|<span data-ttu-id="f7662-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="f7662-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f7662-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f7662-123">DisplayName</span></span>|<span data-ttu-id="f7662-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7662-124">xs:string</span></span>|<span data-ttu-id="f7662-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="f7662-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f7662-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f7662-126">InstanceId</span></span>|<span data-ttu-id="f7662-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7662-127">xs:string</span></span>|<span data-ttu-id="f7662-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="f7662-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f7662-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f7662-129">AppDomain</span></span>|<span data-ttu-id="f7662-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7662-130">xs:string</span></span>|<span data-ttu-id="f7662-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f7662-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
