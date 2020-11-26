---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242104"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="53e33-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="53e33-102">3502 - InferredOperationDescription</span></span>

## <a name="properties"></a><span data-ttu-id="53e33-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="53e33-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53e33-104">ID</span><span class="sxs-lookup"><span data-stu-id="53e33-104">ID</span></span>|<span data-ttu-id="53e33-105">3502</span><span class="sxs-lookup"><span data-stu-id="53e33-105">3502</span></span>|  
|<span data-ttu-id="53e33-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="53e33-106">Keywords</span></span>|<span data-ttu-id="53e33-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="53e33-107">WFServices</span></span>|  
|<span data-ttu-id="53e33-108">Nível</span><span class="sxs-lookup"><span data-stu-id="53e33-108">Level</span></span>|<span data-ttu-id="53e33-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="53e33-109">Information</span></span>|  
|<span data-ttu-id="53e33-110">Canal</span><span class="sxs-lookup"><span data-stu-id="53e33-110">Channel</span></span>|<span data-ttu-id="53e33-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="53e33-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="53e33-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="53e33-112">Description</span></span>  

 <span data-ttu-id="53e33-113">Indica que um OperationDescription foi inferido de WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="53e33-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="53e33-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="53e33-114">Message</span></span>  

 <span data-ttu-id="53e33-115">OperationDescription com o Name='%1 no contrato “%2 " foi inferido de WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="53e33-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="53e33-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="53e33-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="53e33-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="53e33-117">Details</span></span>  
  
|<span data-ttu-id="53e33-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="53e33-118">Data Item Name</span></span>|<span data-ttu-id="53e33-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="53e33-119">Data Item Type</span></span>|<span data-ttu-id="53e33-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="53e33-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="53e33-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="53e33-121">OperationName</span></span>|<span data-ttu-id="53e33-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="53e33-122">xs:string</span></span>|<span data-ttu-id="53e33-123">O nome da operação.</span><span class="sxs-lookup"><span data-stu-id="53e33-123">The name of the operation.</span></span>|  
|<span data-ttu-id="53e33-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="53e33-124">ContractName</span></span>|<span data-ttu-id="53e33-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="53e33-125">xs:string</span></span>|<span data-ttu-id="53e33-126">O nome do contrato.</span><span class="sxs-lookup"><span data-stu-id="53e33-126">The name of the contract.</span></span>|  
|<span data-ttu-id="53e33-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="53e33-127">IsOneWay</span></span>|<span data-ttu-id="53e33-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="53e33-128">xs:string</span></span>|<span data-ttu-id="53e33-129">Retifique ou falso indicando se o contrato é unidirecional.</span><span class="sxs-lookup"><span data-stu-id="53e33-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="53e33-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="53e33-130">AppDomain</span></span>|<span data-ttu-id="53e33-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="53e33-131">xs:string</span></span>|<span data-ttu-id="53e33-132">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="53e33-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
