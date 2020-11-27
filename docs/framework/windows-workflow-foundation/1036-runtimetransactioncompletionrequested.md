---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 96ea253fd61652a3719eaf8b1a4d31aa88337eeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294255"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="76334-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="76334-102">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="76334-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="76334-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76334-104">ID</span><span class="sxs-lookup"><span data-stu-id="76334-104">ID</span></span>|<span data-ttu-id="76334-105">1036</span><span class="sxs-lookup"><span data-stu-id="76334-105">1036</span></span>|  
|<span data-ttu-id="76334-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="76334-106">Keywords</span></span>|<span data-ttu-id="76334-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="76334-107">WFRuntime</span></span>|  
|<span data-ttu-id="76334-108">Nível</span><span class="sxs-lookup"><span data-stu-id="76334-108">Level</span></span>|<span data-ttu-id="76334-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="76334-109">Verbose</span></span>|  
|<span data-ttu-id="76334-110">Canal</span><span class="sxs-lookup"><span data-stu-id="76334-110">Channel</span></span>|<span data-ttu-id="76334-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="76334-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76334-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="76334-112">Description</span></span>  

 <span data-ttu-id="76334-113">Indica que uma atividade agendou a conclusão de transação de runtime.</span><span class="sxs-lookup"><span data-stu-id="76334-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="76334-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="76334-114">Message</span></span>  

 <span data-ttu-id="76334-115">Atividade “%1", DisplayName: “%2", InstanceId: “%3 " agendaram a conclusão de transação de runtime.</span><span class="sxs-lookup"><span data-stu-id="76334-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="76334-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="76334-116">Details</span></span>  
  
|<span data-ttu-id="76334-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="76334-117">Data Item Name</span></span>|<span data-ttu-id="76334-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="76334-118">Data Item Type</span></span>|<span data-ttu-id="76334-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="76334-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="76334-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="76334-120">Activity</span></span>|<span data-ttu-id="76334-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="76334-121">xs:string</span></span>|<span data-ttu-id="76334-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="76334-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="76334-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="76334-123">DisplayName</span></span>|<span data-ttu-id="76334-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="76334-124">xs:string</span></span>|<span data-ttu-id="76334-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="76334-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="76334-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="76334-126">InstanceId</span></span>|<span data-ttu-id="76334-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="76334-127">xs:string</span></span>|<span data-ttu-id="76334-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="76334-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="76334-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="76334-129">AppDomain</span></span>|<span data-ttu-id="76334-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="76334-130">xs:string</span></span>|<span data-ttu-id="76334-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="76334-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
