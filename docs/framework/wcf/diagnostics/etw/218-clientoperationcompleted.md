---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: d74aa77aff7b45b50f6891c999889011d9e03381
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278850"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="98db2-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="98db2-102">218 - ClientOperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="98db2-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="98db2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98db2-104">ID</span><span class="sxs-lookup"><span data-stu-id="98db2-104">ID</span></span>|<span data-ttu-id="98db2-105">218</span><span class="sxs-lookup"><span data-stu-id="98db2-105">218</span></span>|  
|<span data-ttu-id="98db2-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="98db2-106">Keywords</span></span>|<span data-ttu-id="98db2-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="98db2-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="98db2-108">Nível</span><span class="sxs-lookup"><span data-stu-id="98db2-108">Level</span></span>|<span data-ttu-id="98db2-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="98db2-109">Information</span></span>|  
|<span data-ttu-id="98db2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="98db2-110">Channel</span></span>|<span data-ttu-id="98db2-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="98db2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="98db2-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="98db2-112">Description</span></span>  

 <span data-ttu-id="98db2-113">Esse evento é emitido por clientes logo após a conclusão de uma operação.</span><span class="sxs-lookup"><span data-stu-id="98db2-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="98db2-114">Para operações unidirecionais, isso ocorre logo após a mensagem ser enviada com êxito.</span><span class="sxs-lookup"><span data-stu-id="98db2-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="98db2-115">Para operações de solicitação-resposta, isso ocorre depois que a resposta é recebida.</span><span class="sxs-lookup"><span data-stu-id="98db2-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="98db2-116">Mensagem</span><span class="sxs-lookup"><span data-stu-id="98db2-116">Message</span></span>  

 <span data-ttu-id="98db2-117">O cliente concluiu a execução da ação ' %1 ' associada ao contrato ' %2 '.</span><span class="sxs-lookup"><span data-stu-id="98db2-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="98db2-118">A mensagem foi enviada para ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="98db2-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="98db2-119">Detalhes</span><span class="sxs-lookup"><span data-stu-id="98db2-119">Details</span></span>  
  
|<span data-ttu-id="98db2-120">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="98db2-120">Data Item Name</span></span>|<span data-ttu-id="98db2-121">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="98db2-121">Data Item Type</span></span>|<span data-ttu-id="98db2-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="98db2-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="98db2-123">Ação</span><span class="sxs-lookup"><span data-stu-id="98db2-123">Action</span></span>|<span data-ttu-id="98db2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="98db2-124">xs:string</span></span>|<span data-ttu-id="98db2-125">O cabeçalho de ação SOAP da mensagem de saída.</span><span class="sxs-lookup"><span data-stu-id="98db2-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="98db2-126">Nome do Contrato</span><span class="sxs-lookup"><span data-stu-id="98db2-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="98db2-127">O nome do contrato.</span><span class="sxs-lookup"><span data-stu-id="98db2-127">The name of the contract.</span></span> <span data-ttu-id="98db2-128">Exemplo: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="98db2-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="98db2-129">Destino</span><span class="sxs-lookup"><span data-stu-id="98db2-129">Destination</span></span>|`xs:string`|<span data-ttu-id="98db2-130">O endereço do ponto de extremidade de serviço para o qual a mensagem foi enviada.</span><span class="sxs-lookup"><span data-stu-id="98db2-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="98db2-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="98db2-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="98db2-132">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="98db2-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="98db2-133">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="98db2-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="98db2-134">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="98db2-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="98db2-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="98db2-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="98db2-136">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="98db2-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
