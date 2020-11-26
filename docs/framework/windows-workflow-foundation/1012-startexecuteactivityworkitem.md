---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: b9cfceb12d56f93c0f9726849e34f4333f1399ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239634"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="01e74-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="01e74-102">1012 - StartExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="01e74-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="01e74-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01e74-104">ID</span><span class="sxs-lookup"><span data-stu-id="01e74-104">ID</span></span>|<span data-ttu-id="01e74-105">1012</span><span class="sxs-lookup"><span data-stu-id="01e74-105">1012</span></span>|  
|<span data-ttu-id="01e74-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="01e74-106">Keywords</span></span>|<span data-ttu-id="01e74-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="01e74-107">WFRuntime</span></span>|  
|<span data-ttu-id="01e74-108">Nível</span><span class="sxs-lookup"><span data-stu-id="01e74-108">Level</span></span>|<span data-ttu-id="01e74-109">Detalhado</span><span class="sxs-lookup"><span data-stu-id="01e74-109">Verbose</span></span>|  
|<span data-ttu-id="01e74-110">Canal</span><span class="sxs-lookup"><span data-stu-id="01e74-110">Channel</span></span>|<span data-ttu-id="01e74-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="01e74-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="01e74-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="01e74-112">Description</span></span>  

 <span data-ttu-id="01e74-113">Indica que um ExecuteActivityWorkItem está sendo a execução.</span><span class="sxs-lookup"><span data-stu-id="01e74-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="01e74-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="01e74-114">Message</span></span>  

 <span data-ttu-id="01e74-115">Iniciar a execução de um ExecuteActivityWorkItem para atividades “%1 ", DisplayName: “%2", InstanceId: “%3".</span><span class="sxs-lookup"><span data-stu-id="01e74-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="01e74-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="01e74-116">Details</span></span>  
  
|<span data-ttu-id="01e74-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="01e74-117">Data Item Name</span></span>|<span data-ttu-id="01e74-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="01e74-118">Data Item Type</span></span>|<span data-ttu-id="01e74-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="01e74-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="01e74-120">Atividade</span><span class="sxs-lookup"><span data-stu-id="01e74-120">Activity</span></span>|<span data-ttu-id="01e74-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="01e74-121">xs:string</span></span>|<span data-ttu-id="01e74-122">O nome do tipo de atividade.</span><span class="sxs-lookup"><span data-stu-id="01e74-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="01e74-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="01e74-123">DisplayName</span></span>|<span data-ttu-id="01e74-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="01e74-124">xs:string</span></span>|<span data-ttu-id="01e74-125">O nome para exibição de atividade.</span><span class="sxs-lookup"><span data-stu-id="01e74-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="01e74-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="01e74-126">InstanceId</span></span>|<span data-ttu-id="01e74-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="01e74-127">xs:string</span></span>|<span data-ttu-id="01e74-128">A identificação de instância de atividade.</span><span class="sxs-lookup"><span data-stu-id="01e74-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="01e74-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="01e74-129">AppDomain</span></span>|<span data-ttu-id="01e74-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="01e74-130">xs:string</span></span>|<span data-ttu-id="01e74-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="01e74-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
