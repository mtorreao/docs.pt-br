---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 7ba2ada1fbd5217592b4e4e3cffd813ffbe978ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275239"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="5095c-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="5095c-102">1026 - ScheduleTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="5095c-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="5095c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5095c-104">ID</span><span class="sxs-lookup"><span data-stu-id="5095c-104">ID</span></span>|<span data-ttu-id="5095c-105">1026</span><span class="sxs-lookup"><span data-stu-id="5095c-105">1026</span></span>|  
|<span data-ttu-id="5095c-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="5095c-106">Keywords</span></span>|<span data-ttu-id="5095c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5095c-107">WFRuntime</span></span>|  
|<span data-ttu-id="5095c-108">Nível</span><span class="sxs-lookup"><span data-stu-id="5095c-108">Level</span></span>|<span data-ttu-id="5095c-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="5095c-109">Verbose</span></span>|  
|<span data-ttu-id="5095c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5095c-110">Channel</span></span>|<span data-ttu-id="5095c-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="5095c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5095c-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="5095c-112">Description</span></span>  

 <span data-ttu-id="5095c-113">Indica que um TransactionContextWorkItem foi agendada.</span><span class="sxs-lookup"><span data-stu-id="5095c-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5095c-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="5095c-114">Message</span></span>  

 <span data-ttu-id="5095c-115">Um TransactionContextWorkItem foi agendada para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="5095c-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5095c-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5095c-116">Details</span></span>  
  
|<span data-ttu-id="5095c-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="5095c-117">Data Item Name</span></span>|<span data-ttu-id="5095c-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="5095c-118">Data Item Type</span></span>|<span data-ttu-id="5095c-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="5095c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5095c-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="5095c-120">Activity</span></span>|<span data-ttu-id="5095c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5095c-121">xs:string</span></span>|<span data-ttu-id="5095c-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="5095c-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="5095c-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5095c-123">DisplayName</span></span>|<span data-ttu-id="5095c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5095c-124">xs:string</span></span>|<span data-ttu-id="5095c-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="5095c-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="5095c-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5095c-126">InstanceId</span></span>|<span data-ttu-id="5095c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5095c-127">xs:string</span></span>|<span data-ttu-id="5095c-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="5095c-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5095c-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5095c-129">AppDomain</span></span>|<span data-ttu-id="5095c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5095c-130">xs:string</span></span>|<span data-ttu-id="5095c-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5095c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
