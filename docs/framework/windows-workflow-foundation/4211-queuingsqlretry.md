---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ff8a1e099934f5bf71fef0afbb7e54c0d1851fae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267176"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="98dc1-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="98dc1-102">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="98dc1-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="98dc1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98dc1-104">ID</span><span class="sxs-lookup"><span data-stu-id="98dc1-104">ID</span></span>|<span data-ttu-id="98dc1-105">4211</span><span class="sxs-lookup"><span data-stu-id="98dc1-105">4211</span></span>|  
|<span data-ttu-id="98dc1-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="98dc1-106">Keywords</span></span>|<span data-ttu-id="98dc1-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="98dc1-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="98dc1-108">Nível</span><span class="sxs-lookup"><span data-stu-id="98dc1-108">Level</span></span>|<span data-ttu-id="98dc1-109">Aviso</span><span class="sxs-lookup"><span data-stu-id="98dc1-109">Warning</span></span>|  
|<span data-ttu-id="98dc1-110">Canal</span><span class="sxs-lookup"><span data-stu-id="98dc1-110">Channel</span></span>|<span data-ttu-id="98dc1-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração</span><span class="sxs-lookup"><span data-stu-id="98dc1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="98dc1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="98dc1-112">Description</span></span>  

 <span data-ttu-id="98dc1-113">Indica a nova tentativa de enfileiramento SQL.</span><span class="sxs-lookup"><span data-stu-id="98dc1-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="98dc1-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="98dc1-114">Message</span></span>  

 <span data-ttu-id="98dc1-115">Nova tentativa SQL fila com atraso %1 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="98dc1-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="98dc1-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="98dc1-116">Details</span></span>  
  
|<span data-ttu-id="98dc1-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="98dc1-117">Data Item Name</span></span>|<span data-ttu-id="98dc1-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="98dc1-118">Data Item Type</span></span>|<span data-ttu-id="98dc1-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="98dc1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="98dc1-120">Atrasar</span><span class="sxs-lookup"><span data-stu-id="98dc1-120">Delay</span></span>|<span data-ttu-id="98dc1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="98dc1-121">xs:string</span></span>|<span data-ttu-id="98dc1-122">O intervalo entre repetições.</span><span class="sxs-lookup"><span data-stu-id="98dc1-122">The delay between retries.</span></span>|  
|<span data-ttu-id="98dc1-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="98dc1-123">AppDomain</span></span>|<span data-ttu-id="98dc1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="98dc1-124">xs:string</span></span>|<span data-ttu-id="98dc1-125">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="98dc1-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
