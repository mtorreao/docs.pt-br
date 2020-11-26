---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: e7c92dcc9ce472c50af6f0aa26c59f55d62fbb9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239933"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="bed39-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="bed39-102">1002 - WorkflowApplicationTerminated</span></span>

## <a name="properties"></a><span data-ttu-id="bed39-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="bed39-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bed39-104">ID</span><span class="sxs-lookup"><span data-stu-id="bed39-104">ID</span></span>|<span data-ttu-id="bed39-105">1002</span><span class="sxs-lookup"><span data-stu-id="bed39-105">1002</span></span>|  
|<span data-ttu-id="bed39-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="bed39-106">Keywords</span></span>|<span data-ttu-id="bed39-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bed39-107">WFRuntime</span></span>|  
|<span data-ttu-id="bed39-108">Nível</span><span class="sxs-lookup"><span data-stu-id="bed39-108">Level</span></span>|<span data-ttu-id="bed39-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="bed39-109">Information</span></span>|  
|<span data-ttu-id="bed39-110">Canal</span><span class="sxs-lookup"><span data-stu-id="bed39-110">Channel</span></span>|<span data-ttu-id="bed39-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="bed39-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bed39-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="bed39-112">Description</span></span>  

 <span data-ttu-id="bed39-113">Indica que um aplicativo de fluxo de trabalho foi finalizado no estado criticado com uma exceção.</span><span class="sxs-lookup"><span data-stu-id="bed39-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bed39-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="bed39-114">Message</span></span>  

 <span data-ttu-id="bed39-115">Identificação de WorkflowApplication: “%1 " foi encerrado.</span><span class="sxs-lookup"><span data-stu-id="bed39-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="bed39-116">Foi concluído em estado Faulted (com falha) com uma exceção.</span><span class="sxs-lookup"><span data-stu-id="bed39-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bed39-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bed39-117">Details</span></span>  
  
|<span data-ttu-id="bed39-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="bed39-118">Data Item Name</span></span>|<span data-ttu-id="bed39-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="bed39-119">Data Item Type</span></span>|<span data-ttu-id="bed39-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="bed39-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bed39-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="bed39-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="bed39-122">A identificação do aplicativo de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="bed39-122">The workflow application id</span></span>|  
|<span data-ttu-id="bed39-123">Exceção</span><span class="sxs-lookup"><span data-stu-id="bed39-123">Exception</span></span>|`xs:string`|<span data-ttu-id="bed39-124">Os detalhes de exceção para a exceção</span><span class="sxs-lookup"><span data-stu-id="bed39-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="bed39-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bed39-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bed39-126">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bed39-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
