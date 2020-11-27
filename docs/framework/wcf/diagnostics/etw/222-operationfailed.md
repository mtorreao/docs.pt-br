---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: 64b41ee78e943ca16eaa791133454ec62ccf6ed8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263081"
---
# <a name="222---operationfailed"></a><span data-ttu-id="0b13d-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="0b13d-102">222 - OperationFailed</span></span>

## <a name="properties"></a><span data-ttu-id="0b13d-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="0b13d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b13d-104">ID</span><span class="sxs-lookup"><span data-stu-id="0b13d-104">ID</span></span>|<span data-ttu-id="0b13d-105">222</span><span class="sxs-lookup"><span data-stu-id="0b13d-105">222</span></span>|  
|<span data-ttu-id="0b13d-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="0b13d-106">Keywords</span></span>|<span data-ttu-id="0b13d-107">EndToEndMonitoring, HealthMonitoring, solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0b13d-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0b13d-108">Nível</span><span class="sxs-lookup"><span data-stu-id="0b13d-108">Level</span></span>|<span data-ttu-id="0b13d-109">Aviso</span><span class="sxs-lookup"><span data-stu-id="0b13d-109">Warning</span></span>|  
|<span data-ttu-id="0b13d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0b13d-110">Channel</span></span>|<span data-ttu-id="0b13d-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="0b13d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0b13d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="0b13d-112">Description</span></span>  

 <span data-ttu-id="0b13d-113">Esse evento é emitido quando o padrão do modelo de serviço `OperationInvoker` encontrou uma exceção ao invocar seu método.</span><span class="sxs-lookup"><span data-stu-id="0b13d-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="0b13d-114">Observe que as exceções que derivam de `FaultException` fazem com que esse evento não seja emitido.</span><span class="sxs-lookup"><span data-stu-id="0b13d-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0b13d-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="0b13d-115">Message</span></span>  

 <span data-ttu-id="0b13d-116">O método ' %1 ' lançou uma exceção sem tratamento quando invocado pelo OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="0b13d-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="0b13d-117">A duração da chamada do método era ' %2 ' MS.</span><span class="sxs-lookup"><span data-stu-id="0b13d-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0b13d-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0b13d-118">Details</span></span>  
  
|<span data-ttu-id="0b13d-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="0b13d-119">Data Item Name</span></span>|<span data-ttu-id="0b13d-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="0b13d-120">Data Item Type</span></span>|<span data-ttu-id="0b13d-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="0b13d-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0b13d-122">Nome do método</span><span class="sxs-lookup"><span data-stu-id="0b13d-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="0b13d-123">O nome do CLR do método que foi invocado pelo `OperationInvoker` .</span><span class="sxs-lookup"><span data-stu-id="0b13d-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="0b13d-124">Duração</span><span class="sxs-lookup"><span data-stu-id="0b13d-124">Duration</span></span>|`xs:long`|<span data-ttu-id="0b13d-125">O tempo, em milissegundos, necessário `OperationInvoker` para invocar o método.</span><span class="sxs-lookup"><span data-stu-id="0b13d-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="0b13d-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="0b13d-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="0b13d-127">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="0b13d-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0b13d-128">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="0b13d-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0b13d-129">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="0b13d-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0b13d-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0b13d-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0b13d-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0b13d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
