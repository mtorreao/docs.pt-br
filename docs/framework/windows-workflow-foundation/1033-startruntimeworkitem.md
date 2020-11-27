---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: 46a3dc8d313ec72ac90abc2e2e333b274dad2e4c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294294"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="5ef4a-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="5ef4a-102">1033 - StartRuntimeWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="5ef4a-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="5ef4a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ef4a-104">ID</span><span class="sxs-lookup"><span data-stu-id="5ef4a-104">ID</span></span>|<span data-ttu-id="5ef4a-105">1046</span><span class="sxs-lookup"><span data-stu-id="5ef4a-105">1033</span></span>|  
|<span data-ttu-id="5ef4a-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="5ef4a-106">Keywords</span></span>|<span data-ttu-id="5ef4a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5ef4a-107">WFRuntime</span></span>|  
|<span data-ttu-id="5ef4a-108">Nível</span><span class="sxs-lookup"><span data-stu-id="5ef4a-108">Level</span></span>|<span data-ttu-id="5ef4a-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="5ef4a-109">Verbose</span></span>|  
|<span data-ttu-id="5ef4a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5ef4a-110">Channel</span></span>|<span data-ttu-id="5ef4a-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="5ef4a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5ef4a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ef4a-112">Description</span></span>  

 <span data-ttu-id="5ef4a-113">Indica que um RuntimeWorkItem está sendo a execução.</span><span class="sxs-lookup"><span data-stu-id="5ef4a-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5ef4a-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="5ef4a-114">Message</span></span>  

 <span data-ttu-id="5ef4a-115">Iniciar a execução de um item de trabalho de runtime para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="5ef4a-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5ef4a-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5ef4a-116">Details</span></span>  
  
|<span data-ttu-id="5ef4a-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="5ef4a-117">Data Item Name</span></span>|<span data-ttu-id="5ef4a-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="5ef4a-118">Data Item Type</span></span>|<span data-ttu-id="5ef4a-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ef4a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5ef4a-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="5ef4a-120">Activity</span></span>|<span data-ttu-id="5ef4a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ef4a-121">xs:string</span></span>|<span data-ttu-id="5ef4a-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="5ef4a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5ef4a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5ef4a-123">DisplayName</span></span>|<span data-ttu-id="5ef4a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ef4a-124">xs:string</span></span>|<span data-ttu-id="5ef4a-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="5ef4a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5ef4a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5ef4a-126">InstanceId</span></span>|<span data-ttu-id="5ef4a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ef4a-127">xs:string</span></span>|<span data-ttu-id="5ef4a-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="5ef4a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5ef4a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5ef4a-129">AppDomain</span></span>|<span data-ttu-id="5ef4a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ef4a-130">xs:string</span></span>|<span data-ttu-id="5ef4a-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5ef4a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
