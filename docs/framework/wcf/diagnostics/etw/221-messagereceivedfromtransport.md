---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 47e871b70e3ef2419543b4710c2988736665cb46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263094"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="7d3d3-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="7d3d3-102">221 - MessageReceivedFromTransport</span></span>

## <a name="properties"></a><span data-ttu-id="7d3d3-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7d3d3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d3d3-104">ID</span><span class="sxs-lookup"><span data-stu-id="7d3d3-104">ID</span></span>|<span data-ttu-id="7d3d3-105">221</span><span class="sxs-lookup"><span data-stu-id="7d3d3-105">221</span></span>|  
|<span data-ttu-id="7d3d3-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="7d3d3-106">Keywords</span></span>|<span data-ttu-id="7d3d3-107">EndToEndMonitoring, solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7d3d3-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7d3d3-108">Nível</span><span class="sxs-lookup"><span data-stu-id="7d3d3-108">Level</span></span>|<span data-ttu-id="7d3d3-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="7d3d3-109">Information</span></span>|  
|<span data-ttu-id="7d3d3-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7d3d3-110">Channel</span></span>|<span data-ttu-id="7d3d3-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="7d3d3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7d3d3-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d3d3-112">Description</span></span>  

 <span data-ttu-id="7d3d3-113">Esse evento é emitido quando o modelo de serviço recebe uma mensagem do transporte.</span><span class="sxs-lookup"><span data-stu-id="7d3d3-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7d3d3-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="7d3d3-114">Message</span></span>  

 <span data-ttu-id="7d3d3-115">O Dispatcher recebeu uma mensagem do transporte.</span><span class="sxs-lookup"><span data-stu-id="7d3d3-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="7d3d3-116">ID de correlação = = ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="7d3d3-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7d3d3-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7d3d3-117">Details</span></span>  
  
|<span data-ttu-id="7d3d3-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="7d3d3-118">Data Item Name</span></span>|<span data-ttu-id="7d3d3-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="7d3d3-119">Data Item Type</span></span>|<span data-ttu-id="7d3d3-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d3d3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7d3d3-121">ID de Correlação</span><span class="sxs-lookup"><span data-stu-id="7d3d3-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="7d3d3-122">A ID da atividade usada para correlacionar um `MessageSentToTransport` evento de um serviço ou cliente ao seu correspondente `MessageReceivedFromTransport` no outro final.</span><span class="sxs-lookup"><span data-stu-id="7d3d3-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="7d3d3-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="7d3d3-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="7d3d3-124">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="7d3d3-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7d3d3-125">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="7d3d3-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7d3d3-126">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="7d3d3-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7d3d3-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7d3d3-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7d3d3-128">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7d3d3-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
