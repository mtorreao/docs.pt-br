---
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: 6147c70448efb122cb43a2b42a1e9b59980fab29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278941"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="64c2e-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="64c2e-102">214 - OperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="64c2e-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="64c2e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64c2e-104">ID</span><span class="sxs-lookup"><span data-stu-id="64c2e-104">ID</span></span>|<span data-ttu-id="64c2e-105">214</span><span class="sxs-lookup"><span data-stu-id="64c2e-105">214</span></span>|  
|<span data-ttu-id="64c2e-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="64c2e-106">Keywords</span></span>|<span data-ttu-id="64c2e-107">HealthMonitoring, EndToEndMonitoring, solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="64c2e-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="64c2e-108">Nível</span><span class="sxs-lookup"><span data-stu-id="64c2e-108">Level</span></span>|<span data-ttu-id="64c2e-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="64c2e-109">Information</span></span>|  
|<span data-ttu-id="64c2e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="64c2e-110">Channel</span></span>|<span data-ttu-id="64c2e-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="64c2e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="64c2e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="64c2e-112">Description</span></span>  

 <span data-ttu-id="64c2e-113">Esse evento é emitido quando o padrão do modelo de serviço `OperationInvoker` concluiu uma chamada para um método sem que esse método emita uma exceção.</span><span class="sxs-lookup"><span data-stu-id="64c2e-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="64c2e-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="64c2e-114">Message</span></span>  

 <span data-ttu-id="64c2e-115">Um OperationInvoker concluiu a chamada para o método ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="64c2e-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="64c2e-116">A duração da chamada do método era ' %2 ' MS.</span><span class="sxs-lookup"><span data-stu-id="64c2e-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="64c2e-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="64c2e-117">Details</span></span>  
  
|<span data-ttu-id="64c2e-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="64c2e-118">Data Item Name</span></span>|<span data-ttu-id="64c2e-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="64c2e-119">Data Item Type</span></span>|<span data-ttu-id="64c2e-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="64c2e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="64c2e-121">Nome do método</span><span class="sxs-lookup"><span data-stu-id="64c2e-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="64c2e-122">O nome do CLR do método que foi invocado pelo `OperationInvoker` .</span><span class="sxs-lookup"><span data-stu-id="64c2e-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="64c2e-123">Duração</span><span class="sxs-lookup"><span data-stu-id="64c2e-123">Duration</span></span>|`xs:long`|<span data-ttu-id="64c2e-124">O tempo, em milissegundos, necessário `OperationInvoker` para invocar o método.</span><span class="sxs-lookup"><span data-stu-id="64c2e-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="64c2e-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="64c2e-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="64c2e-126">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="64c2e-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="64c2e-127">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="64c2e-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="64c2e-128">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="64c2e-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="64c2e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="64c2e-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="64c2e-130">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="64c2e-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
