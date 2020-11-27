---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 17617e25c5cf8cecae608438529e9ce1a7d506f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251263"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="60e43-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="60e43-102">4203 - RenewLockSystemError</span></span>

## <a name="properties"></a><span data-ttu-id="60e43-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="60e43-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60e43-104">ID</span><span class="sxs-lookup"><span data-stu-id="60e43-104">ID</span></span>|<span data-ttu-id="60e43-105">4203</span><span class="sxs-lookup"><span data-stu-id="60e43-105">4203</span></span>|  
|<span data-ttu-id="60e43-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="60e43-106">Keywords</span></span>|<span data-ttu-id="60e43-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="60e43-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="60e43-108">Nível</span><span class="sxs-lookup"><span data-stu-id="60e43-108">Level</span></span>|<span data-ttu-id="60e43-109">Erro do</span><span class="sxs-lookup"><span data-stu-id="60e43-109">Error</span></span>|  
|<span data-ttu-id="60e43-110">Canal</span><span class="sxs-lookup"><span data-stu-id="60e43-110">Channel</span></span>|<span data-ttu-id="60e43-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="60e43-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="60e43-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="60e43-112">Description</span></span>  

 <span data-ttu-id="60e43-113">Indica que o provedor SQL não estendeu a validade de bloqueio ou devido à validade de bloqueio já passada ou o proprietário de bloqueio foi excluído.</span><span class="sxs-lookup"><span data-stu-id="60e43-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="60e43-114">O SqlWorkflowInstanceStore será anuladas.</span><span class="sxs-lookup"><span data-stu-id="60e43-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="60e43-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="60e43-115">Message</span></span>  

 <span data-ttu-id="60e43-116">Falha em estender a validade do bloqueio; a validade do bloqueio já terminou ou o proprietário do bloqueio foi excluído.</span><span class="sxs-lookup"><span data-stu-id="60e43-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="60e43-117">Anulando SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="60e43-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="60e43-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="60e43-118">Details</span></span>  
  
|<span data-ttu-id="60e43-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="60e43-119">Data Item Name</span></span>|<span data-ttu-id="60e43-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="60e43-120">Data Item Type</span></span>|<span data-ttu-id="60e43-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="60e43-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="60e43-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="60e43-122">AppDomain</span></span>|<span data-ttu-id="60e43-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="60e43-123">xs:string</span></span>|<span data-ttu-id="60e43-124">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="60e43-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
