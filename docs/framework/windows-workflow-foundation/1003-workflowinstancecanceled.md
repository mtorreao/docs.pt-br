---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: bd8abf173ab6588d4a35ba59c6cd14fb53445e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239894"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="55e3b-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="55e3b-102">1003 - WorkflowInstanceCanceled</span></span>

## <a name="properties"></a><span data-ttu-id="55e3b-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="55e3b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55e3b-104">ID</span><span class="sxs-lookup"><span data-stu-id="55e3b-104">ID</span></span>|<span data-ttu-id="55e3b-105">1003</span><span class="sxs-lookup"><span data-stu-id="55e3b-105">1003</span></span>|  
|<span data-ttu-id="55e3b-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="55e3b-106">Keywords</span></span>|<span data-ttu-id="55e3b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="55e3b-107">WFRuntime</span></span>|  
|<span data-ttu-id="55e3b-108">Nível</span><span class="sxs-lookup"><span data-stu-id="55e3b-108">Level</span></span>|<span data-ttu-id="55e3b-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="55e3b-109">Information</span></span>|  
|<span data-ttu-id="55e3b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="55e3b-110">Channel</span></span>|<span data-ttu-id="55e3b-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="55e3b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="55e3b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="55e3b-112">Description</span></span>  

 <span data-ttu-id="55e3b-113">Indica que uma instância de fluxo de trabalho concluído no estado cancelado.</span><span class="sxs-lookup"><span data-stu-id="55e3b-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="55e3b-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="55e3b-114">Message</span></span>  

 <span data-ttu-id="55e3b-115">Identificação de WorkflowInstance: “%1 " terminou no estado cancelado.</span><span class="sxs-lookup"><span data-stu-id="55e3b-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="55e3b-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="55e3b-116">Details</span></span>  
  
|<span data-ttu-id="55e3b-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="55e3b-117">Data Item Name</span></span>|<span data-ttu-id="55e3b-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="55e3b-118">Data Item Type</span></span>|<span data-ttu-id="55e3b-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="55e3b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="55e3b-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="55e3b-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="55e3b-121">A identificação de instância para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="55e3b-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="55e3b-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="55e3b-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="55e3b-123">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="55e3b-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
