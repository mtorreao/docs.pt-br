---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 04c5e0f4fbf3b95485e5bf4aae53aa2e4912d893
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294489"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="7d84e-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="7d84e-102">225 - TraceCorrelationKeys</span></span>

## <a name="properties"></a><span data-ttu-id="7d84e-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7d84e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d84e-104">ID</span><span class="sxs-lookup"><span data-stu-id="7d84e-104">ID</span></span>|<span data-ttu-id="7d84e-105">225</span><span class="sxs-lookup"><span data-stu-id="7d84e-105">225</span></span>|  
|<span data-ttu-id="7d84e-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7d84e-106">Keywords</span></span>|<span data-ttu-id="7d84e-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7d84e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7d84e-108">Nível</span><span class="sxs-lookup"><span data-stu-id="7d84e-108">Level</span></span>|<span data-ttu-id="7d84e-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="7d84e-109">Information</span></span>|  
|<span data-ttu-id="7d84e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7d84e-110">Channel</span></span>|<span data-ttu-id="7d84e-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="7d84e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7d84e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d84e-112">Description</span></span>  

 <span data-ttu-id="7d84e-113">Este evento é emitida quando correlação conteudo base é usada para um serviço de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7d84e-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="7d84e-114">Contém as chaves de correlação que são aplicadas para correlacionar uma mensagem a uma instância.</span><span class="sxs-lookup"><span data-stu-id="7d84e-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7d84e-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="7d84e-115">Message</span></span>  

 <span data-ttu-id="7d84e-116">Chave calculada “%1 " de correlação usando o %2 " dos valores no escopo pai “%3 ".</span><span class="sxs-lookup"><span data-stu-id="7d84e-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7d84e-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7d84e-117">Details</span></span>  
  
|<span data-ttu-id="7d84e-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="7d84e-118">Data Item Name</span></span>|<span data-ttu-id="7d84e-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="7d84e-119">Data Item Type</span></span>|<span data-ttu-id="7d84e-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d84e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7d84e-121">Chave de instância</span><span class="sxs-lookup"><span data-stu-id="7d84e-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="7d84e-122">A tecla que foi gerada de correlação avalia.</span><span class="sxs-lookup"><span data-stu-id="7d84e-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="7d84e-123">Valores</span><span class="sxs-lookup"><span data-stu-id="7d84e-123">Values</span></span>|`xs:string`|<span data-ttu-id="7d84e-124">Os valores que foram usados para calcular a chave de instância de correlação.</span><span class="sxs-lookup"><span data-stu-id="7d84e-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="7d84e-125">Escopo pai</span><span class="sxs-lookup"><span data-stu-id="7d84e-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="7d84e-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="7d84e-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="7d84e-127">Os serviços hospedados da Web, este campo identificam exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="7d84e-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7d84e-128">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="7d84e-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7d84e-129">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="7d84e-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7d84e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7d84e-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7d84e-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7d84e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
