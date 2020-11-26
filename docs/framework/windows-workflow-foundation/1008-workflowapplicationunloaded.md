---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: 6ea121e7901d877d4f0d8f9f5bfd259c2f93696d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239811"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="4531b-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="4531b-102">1008 - WorkflowApplicationUnloaded</span></span>

## <a name="properties"></a><span data-ttu-id="4531b-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="4531b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4531b-104">ID</span><span class="sxs-lookup"><span data-stu-id="4531b-104">ID</span></span>|<span data-ttu-id="4531b-105">1008</span><span class="sxs-lookup"><span data-stu-id="4531b-105">1008</span></span>|  
|<span data-ttu-id="4531b-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="4531b-106">Keywords</span></span>|<span data-ttu-id="4531b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4531b-107">WFRuntime</span></span>|  
|<span data-ttu-id="4531b-108">Nível</span><span class="sxs-lookup"><span data-stu-id="4531b-108">Level</span></span>|<span data-ttu-id="4531b-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="4531b-109">Information</span></span>|  
|<span data-ttu-id="4531b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4531b-110">Channel</span></span>|<span data-ttu-id="4531b-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="4531b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4531b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="4531b-112">Description</span></span>  

 <span data-ttu-id="4531b-113">Indica que um aplicativo de fluxo de trabalho descarregou.</span><span class="sxs-lookup"><span data-stu-id="4531b-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4531b-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="4531b-114">Message</span></span>  

 <span data-ttu-id="4531b-115">Identificação de WorkflowInstance: “%1" foi descarregado.</span><span class="sxs-lookup"><span data-stu-id="4531b-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4531b-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4531b-116">Details</span></span>  
  
|<span data-ttu-id="4531b-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="4531b-117">Data Item Name</span></span>|<span data-ttu-id="4531b-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="4531b-118">Data Item Type</span></span>|<span data-ttu-id="4531b-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="4531b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4531b-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="4531b-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="4531b-121">A identificação de instância para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="4531b-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4531b-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4531b-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4531b-123">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4531b-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
