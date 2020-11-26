---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 3b7210246b7fb754145c8aa6128da3183cea9f91
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239855"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="8ae5b-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="8ae5b-102">1005 - WorkflowApplicationIdled</span></span>

## <a name="properties"></a><span data-ttu-id="8ae5b-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8ae5b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ae5b-104">ID</span><span class="sxs-lookup"><span data-stu-id="8ae5b-104">ID</span></span>|<span data-ttu-id="8ae5b-105">1005</span><span class="sxs-lookup"><span data-stu-id="8ae5b-105">1005</span></span>|  
|<span data-ttu-id="8ae5b-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="8ae5b-106">Keywords</span></span>|<span data-ttu-id="8ae5b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8ae5b-107">WFRuntime</span></span>|  
|<span data-ttu-id="8ae5b-108">Nível</span><span class="sxs-lookup"><span data-stu-id="8ae5b-108">Level</span></span>|<span data-ttu-id="8ae5b-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="8ae5b-109">Information</span></span>|  
|<span data-ttu-id="8ae5b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8ae5b-110">Channel</span></span>|<span data-ttu-id="8ae5b-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="8ae5b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8ae5b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ae5b-112">Description</span></span>  

 <span data-ttu-id="8ae5b-113">Indica que um aplicativo de fluxo de trabalho rodou em marcha lenta.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8ae5b-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="8ae5b-114">Message</span></span>  

 <span data-ttu-id="8ae5b-115">Identificação de WorkflowApplication: “%1 " foi ociosa.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8ae5b-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8ae5b-116">Details</span></span>  
  
|<span data-ttu-id="8ae5b-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="8ae5b-117">Data Item Name</span></span>|<span data-ttu-id="8ae5b-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="8ae5b-118">Data Item Type</span></span>|<span data-ttu-id="8ae5b-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ae5b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8ae5b-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="8ae5b-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="8ae5b-121">A identificação do aplicativo de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="8ae5b-121">The workflow application id</span></span>|  
|<span data-ttu-id="8ae5b-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8ae5b-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8ae5b-123">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
