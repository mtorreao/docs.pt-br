---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: b8bf8431c4e2b82c6aac95820eb45de2a404e976
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294268"
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="59608-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="59608-102">1035 - RuntimeTransactionSet</span></span>

## <a name="properties"></a><span data-ttu-id="59608-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="59608-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59608-104">ID</span><span class="sxs-lookup"><span data-stu-id="59608-104">ID</span></span>|<span data-ttu-id="59608-105">1035</span><span class="sxs-lookup"><span data-stu-id="59608-105">1035</span></span>|  
|<span data-ttu-id="59608-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="59608-106">Keywords</span></span>|<span data-ttu-id="59608-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="59608-107">WFRuntime</span></span>|  
|<span data-ttu-id="59608-108">Nível</span><span class="sxs-lookup"><span data-stu-id="59608-108">Level</span></span>|<span data-ttu-id="59608-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="59608-109">Verbose</span></span>|  
|<span data-ttu-id="59608-110">Canal</span><span class="sxs-lookup"><span data-stu-id="59608-110">Channel</span></span>|<span data-ttu-id="59608-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="59608-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="59608-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="59608-112">Description</span></span>  

 <span data-ttu-id="59608-113">Indica que uma atividade definiu a transação de runtime.</span><span class="sxs-lookup"><span data-stu-id="59608-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="59608-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="59608-114">Message</span></span>  

 <span data-ttu-id="59608-115">A transação de tempo de execução foi definida pela atividade ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="59608-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="59608-116">Execução isolada para a atividade ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 '.</span><span class="sxs-lookup"><span data-stu-id="59608-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="59608-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="59608-117">Details</span></span>  
  
|<span data-ttu-id="59608-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="59608-118">Data Item Name</span></span>|<span data-ttu-id="59608-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="59608-119">Data Item Type</span></span>|<span data-ttu-id="59608-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="59608-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="59608-121">Atividade</span><span class="sxs-lookup"><span data-stu-id="59608-121">Activity</span></span>|<span data-ttu-id="59608-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="59608-122">xs:string</span></span>|<span data-ttu-id="59608-123">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="59608-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="59608-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="59608-124">DisplayName</span></span>|<span data-ttu-id="59608-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="59608-125">xs:string</span></span>|<span data-ttu-id="59608-126">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="59608-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="59608-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="59608-127">InstanceId</span></span>|<span data-ttu-id="59608-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="59608-128">xs:string</span></span>|<span data-ttu-id="59608-129">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="59608-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="59608-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="59608-130">IsolatedActivity</span></span>|<span data-ttu-id="59608-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="59608-131">xs:string</span></span>|<span data-ttu-id="59608-132">O nome do tipo de que a atividade isolada a transação está.</span><span class="sxs-lookup"><span data-stu-id="59608-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="59608-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="59608-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="59608-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="59608-134">xs:string</span></span>|<span data-ttu-id="59608-135">O nome para exibição de que a atividade isolada a transação está.</span><span class="sxs-lookup"><span data-stu-id="59608-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="59608-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="59608-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="59608-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="59608-137">xs:string</span></span>|<span data-ttu-id="59608-138">A identificação de instância de que a atividade isolada a transação está.</span><span class="sxs-lookup"><span data-stu-id="59608-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="59608-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="59608-139">AppDomain</span></span>|<span data-ttu-id="59608-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="59608-140">xs:string</span></span>|<span data-ttu-id="59608-141">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="59608-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
