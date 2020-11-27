---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: 310e91320d27dd9817302fc14ef088d180152b73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263068"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="915e2-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="915e2-102">223 - OperationFaulted</span></span>

## <a name="properties"></a><span data-ttu-id="915e2-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="915e2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="915e2-104">ID</span><span class="sxs-lookup"><span data-stu-id="915e2-104">ID</span></span>|<span data-ttu-id="915e2-105">223</span><span class="sxs-lookup"><span data-stu-id="915e2-105">223</span></span>|  
|<span data-ttu-id="915e2-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="915e2-106">Keywords</span></span>|<span data-ttu-id="915e2-107">EndToEndMonitoring, HealthMonitoring, solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="915e2-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="915e2-108">Nível</span><span class="sxs-lookup"><span data-stu-id="915e2-108">Level</span></span>|<span data-ttu-id="915e2-109">Aviso</span><span class="sxs-lookup"><span data-stu-id="915e2-109">Warning</span></span>|  
|<span data-ttu-id="915e2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="915e2-110">Channel</span></span>|<span data-ttu-id="915e2-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="915e2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="915e2-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="915e2-112">Description</span></span>  

 <span data-ttu-id="915e2-113">Esse evento é emitido quando o padrão do modelo de serviço `OperationInvoker` tiver encontrado uma exceção derivando `FaultException` ao invocar seu método.</span><span class="sxs-lookup"><span data-stu-id="915e2-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="915e2-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="915e2-114">Message</span></span>  

 <span data-ttu-id="915e2-115">O método ' %1 ' lançou uma FaultException quando invocado pelo OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="915e2-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="915e2-116">A duração da chamada do método era ' %2 ' MS.</span><span class="sxs-lookup"><span data-stu-id="915e2-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="915e2-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="915e2-117">Details</span></span>  
  
|<span data-ttu-id="915e2-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="915e2-118">Data Item Name</span></span>|<span data-ttu-id="915e2-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="915e2-119">Data Item Type</span></span>|<span data-ttu-id="915e2-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="915e2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="915e2-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="915e2-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="915e2-122">O nome do CLR do método que foi invocado pelo `OperationInvoker` .</span><span class="sxs-lookup"><span data-stu-id="915e2-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="915e2-123">Duração</span><span class="sxs-lookup"><span data-stu-id="915e2-123">Duration</span></span>|`xs:long`|<span data-ttu-id="915e2-124">O tempo, em milissegundos, necessário `OperationInvoker` para invocar o método.</span><span class="sxs-lookup"><span data-stu-id="915e2-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="915e2-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="915e2-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="915e2-126">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="915e2-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="915e2-127">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="915e2-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="915e2-128">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="915e2-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="915e2-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="915e2-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="915e2-130">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="915e2-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
