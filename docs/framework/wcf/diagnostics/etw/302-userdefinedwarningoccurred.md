---
title: 302 - UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: b942b2e9716713371b8679fc9df9b9634dfc7283
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243437"
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="cfef7-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="cfef7-102">302 - UserDefinedWarningOccurred</span></span>

## <a name="properties"></a><span data-ttu-id="cfef7-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="cfef7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfef7-104">ID</span><span class="sxs-lookup"><span data-stu-id="cfef7-104">ID</span></span>|<span data-ttu-id="cfef7-105">302</span><span class="sxs-lookup"><span data-stu-id="cfef7-105">302</span></span>|  
|<span data-ttu-id="cfef7-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="cfef7-106">Keywords</span></span>|<span data-ttu-id="cfef7-107">Solução de problemas, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="cfef7-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="cfef7-108">Nível</span><span class="sxs-lookup"><span data-stu-id="cfef7-108">Level</span></span>|<span data-ttu-id="cfef7-109">Aviso</span><span class="sxs-lookup"><span data-stu-id="cfef7-109">Warning</span></span>|  
|<span data-ttu-id="cfef7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="cfef7-110">Channel</span></span>|<span data-ttu-id="cfef7-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="cfef7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cfef7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="cfef7-112">Description</span></span>  

 <span data-ttu-id="cfef7-113">Esse evento é emitido a partir do código do usuário.</span><span class="sxs-lookup"><span data-stu-id="cfef7-113">This event is emitted from user code.</span></span> <span data-ttu-id="cfef7-114">Os desenvolvedores podem emitir esse evento quando um evento de aviso definido pelo personalizado ocorrer em seu serviço.</span><span class="sxs-lookup"><span data-stu-id="cfef7-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="cfef7-115">Isso pode ser feito usando as <xref:System.Diagnostics.Eventing> APIs.</span><span class="sxs-lookup"><span data-stu-id="cfef7-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="cfef7-116">Além disso, há um exemplo do WCF que encapsula essa API e demonstra como emitir esse evento corretamente.</span><span class="sxs-lookup"><span data-stu-id="cfef7-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cfef7-117">Mensagem</span><span class="sxs-lookup"><span data-stu-id="cfef7-117">Message</span></span>  

 <span data-ttu-id="cfef7-118">Nome: ' %1 ', referência: ' %2 ', carga: %3</span><span class="sxs-lookup"><span data-stu-id="cfef7-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="cfef7-119">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cfef7-119">Details</span></span>  
  
|<span data-ttu-id="cfef7-120">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="cfef7-120">Data Item Name</span></span>|<span data-ttu-id="cfef7-121">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="cfef7-121">Data Item Type</span></span>|<span data-ttu-id="cfef7-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="cfef7-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cfef7-123">Nome</span><span class="sxs-lookup"><span data-stu-id="cfef7-123">Name</span></span>|`xs:string`|<span data-ttu-id="cfef7-124">O nome definido pelo usuário do evento.</span><span class="sxs-lookup"><span data-stu-id="cfef7-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="cfef7-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="cfef7-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="cfef7-126">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="cfef7-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cfef7-127">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="cfef7-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cfef7-128">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="cfef7-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cfef7-129">Carga útil</span><span class="sxs-lookup"><span data-stu-id="cfef7-129">Payload</span></span>|`xs:string`|<span data-ttu-id="cfef7-130">A carga definida pelo usuário do evento.</span><span class="sxs-lookup"><span data-stu-id="cfef7-130">The user-defined payload of the event.</span></span>|
