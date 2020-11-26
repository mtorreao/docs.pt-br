---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: be97991be9b61908a23486da0ef255ebfbdc5485
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239946"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="7c8e7-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="7c8e7-102">1001 - WorkflowApplicationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="7c8e7-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7c8e7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c8e7-104">ID</span><span class="sxs-lookup"><span data-stu-id="7c8e7-104">ID</span></span>|<span data-ttu-id="7c8e7-105">1001</span><span class="sxs-lookup"><span data-stu-id="7c8e7-105">1001</span></span>|  
|<span data-ttu-id="7c8e7-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7c8e7-106">Keywords</span></span>|<span data-ttu-id="7c8e7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7c8e7-107">WFRuntime</span></span>|  
|<span data-ttu-id="7c8e7-108">Nível</span><span class="sxs-lookup"><span data-stu-id="7c8e7-108">Level</span></span>|<span data-ttu-id="7c8e7-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="7c8e7-109">Information</span></span>|  
|<span data-ttu-id="7c8e7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7c8e7-110">Channel</span></span>|<span data-ttu-id="7c8e7-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="7c8e7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7c8e7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7c8e7-112">Description</span></span>  

 <span data-ttu-id="7c8e7-113">Indica que um aplicativo de fluxo de trabalho concluído no estado fechado.</span><span class="sxs-lookup"><span data-stu-id="7c8e7-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7c8e7-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="7c8e7-114">Message</span></span>  

 <span data-ttu-id="7c8e7-115">Identificação de WorkflowInstance: “%1 " terminou no estado fechado.</span><span class="sxs-lookup"><span data-stu-id="7c8e7-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7c8e7-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7c8e7-116">Details</span></span>  
  
|<span data-ttu-id="7c8e7-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="7c8e7-117">Data Item Name</span></span>|<span data-ttu-id="7c8e7-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="7c8e7-118">Data Item Type</span></span>|<span data-ttu-id="7c8e7-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="7c8e7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7c8e7-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="7c8e7-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="7c8e7-121">A identificação de instância para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="7c8e7-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="7c8e7-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7c8e7-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7c8e7-123">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7c8e7-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
