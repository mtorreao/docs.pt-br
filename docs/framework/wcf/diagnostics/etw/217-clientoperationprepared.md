---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: e8aaf65bdff0718e932d07937e052541b7134f11
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278876"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="1edb7-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="1edb7-102">217 - ClientOperationPrepared</span></span>

## <a name="properties"></a><span data-ttu-id="1edb7-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="1edb7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1edb7-104">ID</span><span class="sxs-lookup"><span data-stu-id="1edb7-104">ID</span></span>|<span data-ttu-id="1edb7-105">217</span><span class="sxs-lookup"><span data-stu-id="1edb7-105">217</span></span>|  
|<span data-ttu-id="1edb7-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1edb7-106">Keywords</span></span>|<span data-ttu-id="1edb7-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1edb7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1edb7-108">Nível</span><span class="sxs-lookup"><span data-stu-id="1edb7-108">Level</span></span>|<span data-ttu-id="1edb7-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="1edb7-109">Information</span></span>|  
|<span data-ttu-id="1edb7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="1edb7-110">Channel</span></span>|<span data-ttu-id="1edb7-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="1edb7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1edb7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="1edb7-112">Description</span></span>  

 <span data-ttu-id="1edb7-113">Esse evento é emitido pelos clientes logo antes de uma operação ser enviada para o serviço.</span><span class="sxs-lookup"><span data-stu-id="1edb7-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1edb7-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="1edb7-114">Message</span></span>  

 <span data-ttu-id="1edb7-115">O cliente está executando a ação ' %1 ' associada ao contrato ' %2 '.</span><span class="sxs-lookup"><span data-stu-id="1edb7-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="1edb7-116">A mensagem será enviada para ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="1edb7-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1edb7-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1edb7-117">Details</span></span>  
  
|<span data-ttu-id="1edb7-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="1edb7-118">Data Item Name</span></span>|<span data-ttu-id="1edb7-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="1edb7-119">Data Item Type</span></span>|<span data-ttu-id="1edb7-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="1edb7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1edb7-121">Ação</span><span class="sxs-lookup"><span data-stu-id="1edb7-121">Action</span></span>|`xs:string`|<span data-ttu-id="1edb7-122">O cabeçalho de ação SOAP da mensagem de saída.</span><span class="sxs-lookup"><span data-stu-id="1edb7-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="1edb7-123">Nome do Contrato</span><span class="sxs-lookup"><span data-stu-id="1edb7-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="1edb7-124">O nome do contrato.</span><span class="sxs-lookup"><span data-stu-id="1edb7-124">The name of the contract.</span></span> <span data-ttu-id="1edb7-125">Exemplo: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="1edb7-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="1edb7-126">Destino</span><span class="sxs-lookup"><span data-stu-id="1edb7-126">Destination</span></span>|`xs:string`|<span data-ttu-id="1edb7-127">O endereço do ponto de extremidade de serviço ao qual a mensagem é enviada.</span><span class="sxs-lookup"><span data-stu-id="1edb7-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="1edb7-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="1edb7-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="1edb7-129">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="1edb7-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1edb7-130">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="1edb7-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1edb7-131">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="1edb7-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1edb7-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1edb7-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1edb7-133">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1edb7-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
