---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: b3e9e1a48951ad5a2e5e7820dc1828c20e310635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278902"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="776fd-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="776fd-102">216 - MessageSentByTransport</span></span>

## <a name="properties"></a><span data-ttu-id="776fd-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="776fd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="776fd-104">ID</span><span class="sxs-lookup"><span data-stu-id="776fd-104">ID</span></span>|<span data-ttu-id="776fd-105">216</span><span class="sxs-lookup"><span data-stu-id="776fd-105">216</span></span>|  
|<span data-ttu-id="776fd-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="776fd-106">Keywords</span></span>|<span data-ttu-id="776fd-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="776fd-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="776fd-108">Nível</span><span class="sxs-lookup"><span data-stu-id="776fd-108">Level</span></span>|<span data-ttu-id="776fd-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="776fd-109">Information</span></span>|  
|<span data-ttu-id="776fd-110">Canal</span><span class="sxs-lookup"><span data-stu-id="776fd-110">Channel</span></span>|<span data-ttu-id="776fd-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="776fd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="776fd-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="776fd-112">Description</span></span>  

 <span data-ttu-id="776fd-113">Esse evento ocorre quando um transporte baseado em TCP envia uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="776fd-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="776fd-114">Observe que, no nível de transporte, várias mensagens podem ser trocadas entre clientes e serviços para uma única operação.</span><span class="sxs-lookup"><span data-stu-id="776fd-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="776fd-115">Isso pode ser devido ao comportamento da infraestrutura, a segurança é um bom exemplo.</span><span class="sxs-lookup"><span data-stu-id="776fd-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="776fd-116">Portanto, o número de eventos **MessageSentByTransport** emitidos varia de acordo com a associação de seu serviço e sua configuração.</span><span class="sxs-lookup"><span data-stu-id="776fd-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="776fd-117">Mensagem</span><span class="sxs-lookup"><span data-stu-id="776fd-117">Message</span></span>  

 <span data-ttu-id="776fd-118">O transporte enviou uma mensagem para ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="776fd-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="776fd-119">Detalhes</span><span class="sxs-lookup"><span data-stu-id="776fd-119">Details</span></span>  
  
|<span data-ttu-id="776fd-120">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="776fd-120">Data Item Name</span></span>|<span data-ttu-id="776fd-121">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="776fd-121">Data Item Type</span></span>|<span data-ttu-id="776fd-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="776fd-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="776fd-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="776fd-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="776fd-124">O endereço para o qual a mensagem de solicitação foi enviada.</span><span class="sxs-lookup"><span data-stu-id="776fd-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="776fd-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="776fd-125">HostReference</span></span>|<span data-ttu-id="776fd-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="776fd-126">xs:string</span></span>|<span data-ttu-id="776fd-127">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="776fd-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="776fd-128">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="776fd-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="776fd-129">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="776fd-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="776fd-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="776fd-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="776fd-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="776fd-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
