---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: cb5671ce7a30a7096104ba0ca6c4f36bed6b93f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275226"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="8704e-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="8704e-102">1027 - StartTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="8704e-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8704e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8704e-104">ID</span><span class="sxs-lookup"><span data-stu-id="8704e-104">ID</span></span>|<span data-ttu-id="8704e-105">1027</span><span class="sxs-lookup"><span data-stu-id="8704e-105">1027</span></span>|  
|<span data-ttu-id="8704e-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="8704e-106">Keywords</span></span>|<span data-ttu-id="8704e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8704e-107">WFRuntime</span></span>|  
|<span data-ttu-id="8704e-108">Nível</span><span class="sxs-lookup"><span data-stu-id="8704e-108">Level</span></span>|<span data-ttu-id="8704e-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="8704e-109">Verbose</span></span>|  
|<span data-ttu-id="8704e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8704e-110">Channel</span></span>|<span data-ttu-id="8704e-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="8704e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8704e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="8704e-112">Description</span></span>  

 <span data-ttu-id="8704e-113">Indica que um TransactionContextWorkItem está sendo a execução.</span><span class="sxs-lookup"><span data-stu-id="8704e-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8704e-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="8704e-114">Message</span></span>  

 <span data-ttu-id="8704e-115">Iniciar a execução de um TransactionContextWorkItem para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="8704e-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8704e-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8704e-116">Details</span></span>  
  
|<span data-ttu-id="8704e-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="8704e-117">Data Item Name</span></span>|<span data-ttu-id="8704e-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="8704e-118">Data Item Type</span></span>|<span data-ttu-id="8704e-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="8704e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8704e-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="8704e-120">Activity</span></span>|<span data-ttu-id="8704e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8704e-121">xs:string</span></span>|<span data-ttu-id="8704e-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="8704e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8704e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8704e-123">DisplayName</span></span>|<span data-ttu-id="8704e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8704e-124">xs:string</span></span>|<span data-ttu-id="8704e-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="8704e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8704e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8704e-126">InstanceId</span></span>|<span data-ttu-id="8704e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8704e-127">xs:string</span></span>|<span data-ttu-id="8704e-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="8704e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8704e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8704e-129">AppDomain</span></span>|<span data-ttu-id="8704e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8704e-130">xs:string</span></span>|<span data-ttu-id="8704e-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8704e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
