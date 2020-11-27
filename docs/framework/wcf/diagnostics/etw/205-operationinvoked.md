---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: c36294a4a430c3e372e8213246e85dba45ce03c8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286013"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="22335-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="22335-102">205 - OperationInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="22335-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="22335-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22335-104">ID</span><span class="sxs-lookup"><span data-stu-id="22335-104">ID</span></span>|<span data-ttu-id="22335-105">205</span><span class="sxs-lookup"><span data-stu-id="22335-105">205</span></span>|  
|<span data-ttu-id="22335-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="22335-106">Keywords</span></span>|<span data-ttu-id="22335-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="22335-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="22335-108">Nível</span><span class="sxs-lookup"><span data-stu-id="22335-108">Level</span></span>|<span data-ttu-id="22335-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="22335-109">Information</span></span>|  
|<span data-ttu-id="22335-110">Canal</span><span class="sxs-lookup"><span data-stu-id="22335-110">Channel</span></span>|<span data-ttu-id="22335-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="22335-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="22335-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="22335-112">Description</span></span>  

 <span data-ttu-id="22335-113">Esse evento é emitido logo antes de o padrão do modelo de serviço `OperationInvoker` iniciar uma chamada para um método.</span><span class="sxs-lookup"><span data-stu-id="22335-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="22335-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="22335-114">Message</span></span>  

 <span data-ttu-id="22335-115">Um OperationInvoker invocou o método ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="22335-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="22335-116">Informações do chamador: ' %2 '.</span><span class="sxs-lookup"><span data-stu-id="22335-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="22335-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="22335-117">Details</span></span>  
  
|<span data-ttu-id="22335-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="22335-118">Data Item Name</span></span>|<span data-ttu-id="22335-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="22335-119">Data Item Type</span></span>|<span data-ttu-id="22335-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="22335-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="22335-121">Nome do método</span><span class="sxs-lookup"><span data-stu-id="22335-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="22335-122">O nome do CLR do método que foi invocado pelo `OperationInvoker` .</span><span class="sxs-lookup"><span data-stu-id="22335-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="22335-123">Informações de chamador</span><span class="sxs-lookup"><span data-stu-id="22335-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="22335-124">O endereço IP e o número da porta do cliente no formato ' IPAddress: PortNumber '.</span><span class="sxs-lookup"><span data-stu-id="22335-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="22335-125">Os dois valores são recuperados da propriedade de mensagem ' System. ServiceModel. Channels. RemoteEndpointMessageProperty ' dentro do contexto de operação.</span><span class="sxs-lookup"><span data-stu-id="22335-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="22335-126">Observe que, para associações não TCP, esse valor `null` .</span><span class="sxs-lookup"><span data-stu-id="22335-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="22335-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="22335-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="22335-128">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="22335-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="22335-129">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="22335-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="22335-130">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="22335-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="22335-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="22335-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="22335-132">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="22335-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
