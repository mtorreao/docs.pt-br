---
title: 303 - UserDefinedInformationEventOccured
ms.date: 03/30/2017
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
ms.openlocfilehash: 8597d84184caea9fc5dc7778cfc6d05e7dc592db
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243424"
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="3b033-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="3b033-102">303 - UserDefinedInformationEventOccured</span></span>

## <a name="properties"></a><span data-ttu-id="3b033-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="3b033-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b033-104">ID</span><span class="sxs-lookup"><span data-stu-id="3b033-104">ID</span></span>|<span data-ttu-id="3b033-105">303</span><span class="sxs-lookup"><span data-stu-id="3b033-105">303</span></span>|  
|<span data-ttu-id="3b033-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="3b033-106">Keywords</span></span>|<span data-ttu-id="3b033-107">Solução de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="3b033-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="3b033-108">Nível</span><span class="sxs-lookup"><span data-stu-id="3b033-108">Level</span></span>|<span data-ttu-id="3b033-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="3b033-109">Information</span></span>|  
|<span data-ttu-id="3b033-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3b033-110">Channel</span></span>|<span data-ttu-id="3b033-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="3b033-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3b033-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b033-112">Description</span></span>  

 <span data-ttu-id="3b033-113">Esse evento é emitido a partir do código do usuário.</span><span class="sxs-lookup"><span data-stu-id="3b033-113">This event is emitted from user code.</span></span> <span data-ttu-id="3b033-114">Os desenvolvedores podem emitir esse evento quando um evento informativo definido por personalizado ocorrer em seu serviço.</span><span class="sxs-lookup"><span data-stu-id="3b033-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="3b033-115">Isso pode ser feito usando as <xref:System.Diagnostics.Eventing> APIs.</span><span class="sxs-lookup"><span data-stu-id="3b033-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="3b033-116">Além disso, há um exemplo do WCF que encapsula essa API e demonstra como emitir esse evento corretamente.</span><span class="sxs-lookup"><span data-stu-id="3b033-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3b033-117">Mensagem</span><span class="sxs-lookup"><span data-stu-id="3b033-117">Message</span></span>  

 <span data-ttu-id="3b033-118">Nome: ' %1 ', referência: ' %2 ', carga: %3</span><span class="sxs-lookup"><span data-stu-id="3b033-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="3b033-119">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3b033-119">Details</span></span>  
  
|<span data-ttu-id="3b033-120">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="3b033-120">Data Item Name</span></span>|<span data-ttu-id="3b033-121">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="3b033-121">Data Item Type</span></span>|<span data-ttu-id="3b033-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b033-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3b033-123">Nome</span><span class="sxs-lookup"><span data-stu-id="3b033-123">Name</span></span>|`xs:string`|<span data-ttu-id="3b033-124">O nome definido pelo usuário do evento</span><span class="sxs-lookup"><span data-stu-id="3b033-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="3b033-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="3b033-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="3b033-126">Os serviços hospedados da Web, este campo identificam exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="3b033-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3b033-127">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="3b033-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3b033-128">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="3b033-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3b033-129">Carga útil</span><span class="sxs-lookup"><span data-stu-id="3b033-129">Payload</span></span>|`xs:string`|<span data-ttu-id="3b033-130">A carga definida pelo usuário do evento.</span><span class="sxs-lookup"><span data-stu-id="3b033-130">The user-defined payload of the event.</span></span>|
