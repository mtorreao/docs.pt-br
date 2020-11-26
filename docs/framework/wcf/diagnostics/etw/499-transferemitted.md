---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: dc47aa36b5a409c89aaf7963ce51f11cdf84b0fc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247571"
---
# <a name="499---transferemitted"></a><span data-ttu-id="561cb-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="561cb-102">499 - TransferEmitted</span></span>

## <a name="properties"></a><span data-ttu-id="561cb-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="561cb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="561cb-104">ID</span><span class="sxs-lookup"><span data-stu-id="561cb-104">ID</span></span>|<span data-ttu-id="561cb-105">499</span><span class="sxs-lookup"><span data-stu-id="561cb-105">499</span></span>|  
|<span data-ttu-id="561cb-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="561cb-106">Keywords</span></span>|<span data-ttu-id="561cb-107">Solução de problemas, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="561cb-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="561cb-108">Nível</span><span class="sxs-lookup"><span data-stu-id="561cb-108">Level</span></span>|<span data-ttu-id="561cb-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="561cb-109">LogAlways</span></span>|  
|<span data-ttu-id="561cb-110">Canal</span><span class="sxs-lookup"><span data-stu-id="561cb-110">Channel</span></span>|<span data-ttu-id="561cb-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="561cb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="561cb-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="561cb-112">Description</span></span>  

 <span data-ttu-id="561cb-113">Esse evento é emitido quando ocorre o evento de transferência.</span><span class="sxs-lookup"><span data-stu-id="561cb-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="561cb-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="561cb-114">Message</span></span>  

 <span data-ttu-id="561cb-115">Evento de transferência emitido.</span><span class="sxs-lookup"><span data-stu-id="561cb-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="561cb-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="561cb-116">Details</span></span>  
  
|<span data-ttu-id="561cb-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="561cb-117">Data Item Name</span></span>|<span data-ttu-id="561cb-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="561cb-118">Data Item Type</span></span>|<span data-ttu-id="561cb-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="561cb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="561cb-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="561cb-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="561cb-121">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="561cb-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="561cb-122">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="561cb-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="561cb-123">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="561cb-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="561cb-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="561cb-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="561cb-125">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="561cb-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
