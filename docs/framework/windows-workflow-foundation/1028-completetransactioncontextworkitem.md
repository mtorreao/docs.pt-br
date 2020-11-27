---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 2fc509dac7e13f30f74c24d8b98cba55ed5f8e1d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275109"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="fe650-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="fe650-102">1028 - CompleteTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="fe650-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="fe650-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe650-104">ID</span><span class="sxs-lookup"><span data-stu-id="fe650-104">ID</span></span>|<span data-ttu-id="fe650-105">1028</span><span class="sxs-lookup"><span data-stu-id="fe650-105">1028</span></span>|  
|<span data-ttu-id="fe650-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="fe650-106">Keywords</span></span>|<span data-ttu-id="fe650-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fe650-107">WFRuntime</span></span>|  
|<span data-ttu-id="fe650-108">Nível</span><span class="sxs-lookup"><span data-stu-id="fe650-108">Level</span></span>|<span data-ttu-id="fe650-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="fe650-109">Verbose</span></span>|  
|<span data-ttu-id="fe650-110">Canal</span><span class="sxs-lookup"><span data-stu-id="fe650-110">Channel</span></span>|<span data-ttu-id="fe650-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="fe650-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe650-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe650-112">Description</span></span>  

 <span data-ttu-id="fe650-113">Indica que um TransactionContextWorkItem terminado.</span><span class="sxs-lookup"><span data-stu-id="fe650-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fe650-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="fe650-114">Message</span></span>  

 <span data-ttu-id="fe650-115">Um TransactionContextWorkItem concluiu para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="fe650-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fe650-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fe650-116">Details</span></span>  
  
|<span data-ttu-id="fe650-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="fe650-117">Data Item Name</span></span>|<span data-ttu-id="fe650-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="fe650-118">Data Item Type</span></span>|<span data-ttu-id="fe650-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe650-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fe650-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="fe650-120">Activity</span></span>|<span data-ttu-id="fe650-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe650-121">xs:string</span></span>|<span data-ttu-id="fe650-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="fe650-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fe650-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fe650-123">DisplayName</span></span>|<span data-ttu-id="fe650-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe650-124">xs:string</span></span>|<span data-ttu-id="fe650-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="fe650-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fe650-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fe650-126">InstanceId</span></span>|<span data-ttu-id="fe650-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe650-127">xs:string</span></span>|<span data-ttu-id="fe650-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="fe650-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fe650-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fe650-129">AppDomain</span></span>|<span data-ttu-id="fe650-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe650-130">xs:string</span></span>|<span data-ttu-id="fe650-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fe650-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
