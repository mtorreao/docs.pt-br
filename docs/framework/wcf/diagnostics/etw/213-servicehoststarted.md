---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 87a98d30f5ecde6f81580a95e337df22341c23d4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279019"
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="e5753-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="e5753-102">213 - ServiceHostStarted</span></span>

## <a name="properties"></a><span data-ttu-id="e5753-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="e5753-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5753-104">ID</span><span class="sxs-lookup"><span data-stu-id="e5753-104">ID</span></span>|<span data-ttu-id="e5753-105">213</span><span class="sxs-lookup"><span data-stu-id="e5753-105">213</span></span>|  
|<span data-ttu-id="e5753-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="e5753-106">Keywords</span></span>|<span data-ttu-id="e5753-107">EndToEndMonitoring, HealthMonitoring, solução de problemas, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="e5753-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="e5753-108">Nível</span><span class="sxs-lookup"><span data-stu-id="e5753-108">Level</span></span>|<span data-ttu-id="e5753-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="e5753-109">LogAlways</span></span>|  
|<span data-ttu-id="e5753-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e5753-110">Channel</span></span>|<span data-ttu-id="e5753-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="e5753-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e5753-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5753-112">Description</span></span>  

 <span data-ttu-id="e5753-113">Esse evento é emitido quando um host de serviço hospedado na Web é iniciado.</span><span class="sxs-lookup"><span data-stu-id="e5753-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="e5753-114">Isso normalmente acontece quando o serviço é ativado por uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="e5753-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="e5753-115">Também pode acontecer se o serviço estiver configurado para ser iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e5753-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e5753-116">Mensagem</span><span class="sxs-lookup"><span data-stu-id="e5753-116">Message</span></span>  

 <span data-ttu-id="e5753-117">ServiceHost iniciado: ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="e5753-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e5753-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e5753-118">Details</span></span>  
  
|<span data-ttu-id="e5753-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="e5753-119">Data Item Name</span></span>|<span data-ttu-id="e5753-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="e5753-120">Data Item Type</span></span>|<span data-ttu-id="e5753-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5753-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e5753-122">Nome do tipo de serviço</span><span class="sxs-lookup"><span data-stu-id="e5753-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="e5753-123">O CLR FullName do tipo de implementação de serviço.</span><span class="sxs-lookup"><span data-stu-id="e5753-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="e5753-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="e5753-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="e5753-125">Os serviços hospedados da Web, este campo identificam exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="e5753-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e5753-126">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="e5753-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e5753-127">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="e5753-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e5753-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e5753-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e5753-129">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e5753-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
