---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 9995823753fc78ca3f278cd635fcf6c7d2b84325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238932"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="e077c-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="e077c-102">1041 - WorkflowApplicationPersistableIdle</span></span>

## <a name="properties"></a><span data-ttu-id="e077c-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e077c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e077c-104">ID</span><span class="sxs-lookup"><span data-stu-id="e077c-104">ID</span></span>|<span data-ttu-id="e077c-105">1041</span><span class="sxs-lookup"><span data-stu-id="e077c-105">1041</span></span>|  
|<span data-ttu-id="e077c-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="e077c-106">Keywords</span></span>|<span data-ttu-id="e077c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e077c-107">WFRuntime</span></span>|  
|<span data-ttu-id="e077c-108">Nível</span><span class="sxs-lookup"><span data-stu-id="e077c-108">Level</span></span>|<span data-ttu-id="e077c-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="e077c-109">Information</span></span>|  
|<span data-ttu-id="e077c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e077c-110">Channel</span></span>|<span data-ttu-id="e077c-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="e077c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e077c-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e077c-112">Description</span></span>  

 <span data-ttu-id="e077c-113">Indica que um aplicativo de fluxo de trabalho estiver ocioso e persistable.</span><span class="sxs-lookup"><span data-stu-id="e077c-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="e077c-114">O aplicativo de fluxo de trabalho será rodado em marcha lento ou persistente.</span><span class="sxs-lookup"><span data-stu-id="e077c-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e077c-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="e077c-115">Message</span></span>  

 <span data-ttu-id="e077c-116">WorkflowApplication ID: ' %1 ' está ociosa e persistente.</span><span class="sxs-lookup"><span data-stu-id="e077c-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="e077c-117">A seguinte ação será executada: %2.</span><span class="sxs-lookup"><span data-stu-id="e077c-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e077c-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e077c-118">Details</span></span>  
  
|<span data-ttu-id="e077c-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="e077c-119">Data Item Name</span></span>|<span data-ttu-id="e077c-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="e077c-120">Data Item Type</span></span>|<span data-ttu-id="e077c-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="e077c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e077c-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="e077c-122">WorkflowApplicationId</span></span>|<span data-ttu-id="e077c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e077c-123">xs:string</span></span>|<span data-ttu-id="e077c-124">A identificação do aplicativo de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="e077c-124">The workflow application id</span></span>|  
|<span data-ttu-id="e077c-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="e077c-125">ActionTaken</span></span>|<span data-ttu-id="e077c-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e077c-126">xs:string</span></span>|<span data-ttu-id="e077c-127">A ação a ser tomada no aplicativo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e077c-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="e077c-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e077c-128">AppDomain</span></span>|<span data-ttu-id="e077c-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="e077c-129">xs:string</span></span>|<span data-ttu-id="e077c-130">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e077c-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
