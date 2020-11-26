---
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 26b860b88313a971960a65b599562ef1ccb4e7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243515"
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="a2129-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="a2129-102">224 - MessageThrottleAtSeventyPercent</span></span>

## <a name="properties"></a><span data-ttu-id="a2129-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a2129-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2129-104">ID</span><span class="sxs-lookup"><span data-stu-id="a2129-104">ID</span></span>|<span data-ttu-id="a2129-105">224</span><span class="sxs-lookup"><span data-stu-id="a2129-105">224</span></span>|  
|<span data-ttu-id="a2129-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a2129-106">Keywords</span></span>|<span data-ttu-id="a2129-107">EndToEndMonitoring, HealthMonitoring, solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a2129-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a2129-108">Nível</span><span class="sxs-lookup"><span data-stu-id="a2129-108">Level</span></span>|<span data-ttu-id="a2129-109">Aviso</span><span class="sxs-lookup"><span data-stu-id="a2129-109">Warning</span></span>|  
|<span data-ttu-id="a2129-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a2129-110">Channel</span></span>|<span data-ttu-id="a2129-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="a2129-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a2129-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a2129-112">Description</span></span>  

 <span data-ttu-id="a2129-113">Quando uma das principais restrições de serviço for excedida, o `MessageThrottleExceeded` evento será emitido.</span><span class="sxs-lookup"><span data-stu-id="a2129-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="a2129-114">Quando o pico de atividade é lento e o valor atual da limitação está em 70% do limite atual, esse evento é emitido.</span><span class="sxs-lookup"><span data-stu-id="a2129-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="a2129-115">Observe que esse evento é emitido apenas uma vez, pois a atividade está lenta.</span><span class="sxs-lookup"><span data-stu-id="a2129-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="a2129-116">Se o valor atual focalizar na marca de porcentagem de 70, (por exemplo, 70, 69, 70, 71, 70, 69), somente a primeira ocorrência de 70% resultará em um evento.</span><span class="sxs-lookup"><span data-stu-id="a2129-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="a2129-117">Depois que esse evento é emitido, ocorrências futuras de exceder o limite do acelerador resulta em um `MessageThrottleExceeded` evento.</span><span class="sxs-lookup"><span data-stu-id="a2129-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a2129-118">Mensagem</span><span class="sxs-lookup"><span data-stu-id="a2129-118">Message</span></span>  

 <span data-ttu-id="a2129-119">O limite de ' %2 ' do acelerador ' %1 ' está em 70%%.</span><span class="sxs-lookup"><span data-stu-id="a2129-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a2129-120">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a2129-120">Details</span></span>  
  
|<span data-ttu-id="a2129-121">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="a2129-121">Data Item Name</span></span>|<span data-ttu-id="a2129-122">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="a2129-122">Data Item Type</span></span>|<span data-ttu-id="a2129-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="a2129-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a2129-124">Nome do acelerador</span><span class="sxs-lookup"><span data-stu-id="a2129-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="a2129-125">O nome do limite que foi excedido.</span><span class="sxs-lookup"><span data-stu-id="a2129-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="a2129-126">`MaxConcurrentCalls`Ou, `MaxConcurrentInstances` , ou `MaxConcurrentSessions` ,</span><span class="sxs-lookup"><span data-stu-id="a2129-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="a2129-127">Limite</span><span class="sxs-lookup"><span data-stu-id="a2129-127">Limit</span></span>|`xs:long`|<span data-ttu-id="a2129-128">O limite atualmente configurado da limitação.</span><span class="sxs-lookup"><span data-stu-id="a2129-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="a2129-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="a2129-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="a2129-130">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="a2129-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a2129-131">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="a2129-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a2129-132">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="a2129-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a2129-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a2129-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a2129-134">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a2129-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
