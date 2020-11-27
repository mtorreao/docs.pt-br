---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: bd3e7539922e6c430c4ffe5bd96ef1ac7dbd098f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261157"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="cd056-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="cd056-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="cd056-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="cd056-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd056-104">ID</span><span class="sxs-lookup"><span data-stu-id="cd056-104">ID</span></span>|<span data-ttu-id="cd056-105">3552</span><span class="sxs-lookup"><span data-stu-id="cd056-105">3552</span></span>|  
|<span data-ttu-id="cd056-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="cd056-106">Keywords</span></span>|<span data-ttu-id="cd056-107">Cota, WFServices</span><span class="sxs-lookup"><span data-stu-id="cd056-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="cd056-108">Nível</span><span class="sxs-lookup"><span data-stu-id="cd056-108">Level</span></span>|<span data-ttu-id="cd056-109">Aviso</span><span class="sxs-lookup"><span data-stu-id="cd056-109">Warning</span></span>|  
|<span data-ttu-id="cd056-110">Canal</span><span class="sxs-lookup"><span data-stu-id="cd056-110">Channel</span></span>|<span data-ttu-id="cd056-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="cd056-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cd056-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="cd056-112">Description</span></span>  

 <span data-ttu-id="cd056-113">Indica que o limite de “MaxPendingMessagesPerChannel” de regulador de pressão foi atingido.</span><span class="sxs-lookup"><span data-stu-id="cd056-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cd056-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="cd056-114">Message</span></span>  

 <span data-ttu-id="cd056-115">O regulador de pressão “MaxPendingMessagesPerChannel” limite de “%1 " foi atingido.</span><span class="sxs-lookup"><span data-stu-id="cd056-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="cd056-116">Para aumentar esse limite, ajuste a propriedade MaxPendingMessagesPerChannel no BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="cd056-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cd056-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cd056-117">Details</span></span>  
  
|<span data-ttu-id="cd056-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="cd056-118">Data Item Name</span></span>|<span data-ttu-id="cd056-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="cd056-119">Data Item Type</span></span>|<span data-ttu-id="cd056-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="cd056-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cd056-121">Limite</span><span class="sxs-lookup"><span data-stu-id="cd056-121">Limit</span></span>|<span data-ttu-id="cd056-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="cd056-122">xs:string</span></span>|<span data-ttu-id="cd056-123">O limite de regulador de pressão de MaxPendingMessagesPerChannel.</span><span class="sxs-lookup"><span data-stu-id="cd056-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="cd056-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cd056-124">AppDomain</span></span>|<span data-ttu-id="cd056-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="cd056-125">xs:string</span></span>|<span data-ttu-id="cd056-126">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cd056-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
