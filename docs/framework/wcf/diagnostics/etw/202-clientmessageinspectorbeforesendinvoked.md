---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: f05a0f817b8cb4857a4fa50eada15d3ff9e06855
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266617"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="f03ec-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="f03ec-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="f03ec-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="f03ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f03ec-104">ID</span><span class="sxs-lookup"><span data-stu-id="f03ec-104">ID</span></span>|<span data-ttu-id="f03ec-105">202</span><span class="sxs-lookup"><span data-stu-id="f03ec-105">202</span></span>|  
|<span data-ttu-id="f03ec-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="f03ec-106">Keywords</span></span>|<span data-ttu-id="f03ec-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f03ec-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f03ec-108">Nível</span><span class="sxs-lookup"><span data-stu-id="f03ec-108">Level</span></span>|<span data-ttu-id="f03ec-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="f03ec-109">Information</span></span>|  
|<span data-ttu-id="f03ec-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f03ec-110">Channel</span></span>|<span data-ttu-id="f03ec-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="f03ec-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f03ec-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f03ec-112">Description</span></span>  

 <span data-ttu-id="f03ec-113">Esse evento é emitido depois que o modelo de serviço invoca o `BeforeSendRequest` método em um inspetor de mensagem do cliente.</span><span class="sxs-lookup"><span data-stu-id="f03ec-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f03ec-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f03ec-114">Message</span></span>  

 <span data-ttu-id="f03ec-115">O Dispatcher invocou ' BeforeSendRequest ' em um ClientMessageInspector do tipo ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="f03ec-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f03ec-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f03ec-116">Details</span></span>  
  
|<span data-ttu-id="f03ec-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="f03ec-117">Data Item Name</span></span>|<span data-ttu-id="f03ec-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="f03ec-118">Data Item Type</span></span>|<span data-ttu-id="f03ec-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="f03ec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f03ec-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f03ec-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f03ec-121">O CLR FullName do tipo do Inspetor invocado.</span><span class="sxs-lookup"><span data-stu-id="f03ec-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="f03ec-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f03ec-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f03ec-123">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="f03ec-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f03ec-124">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="f03ec-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f03ec-125">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="f03ec-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f03ec-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f03ec-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f03ec-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f03ec-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
