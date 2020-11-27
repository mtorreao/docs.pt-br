---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 4aa0f41b0b772551d9257920e5c15051961b7332
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267813"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="cb2b7-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="cb2b7-102">208 - MessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="cb2b7-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="cb2b7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb2b7-104">ID</span><span class="sxs-lookup"><span data-stu-id="cb2b7-104">ID</span></span>|<span data-ttu-id="cb2b7-105">208</span><span class="sxs-lookup"><span data-stu-id="cb2b7-105">208</span></span>|  
|<span data-ttu-id="cb2b7-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="cb2b7-106">Keywords</span></span>|<span data-ttu-id="cb2b7-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cb2b7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cb2b7-108">Nível</span><span class="sxs-lookup"><span data-stu-id="cb2b7-108">Level</span></span>|<span data-ttu-id="cb2b7-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="cb2b7-109">Information</span></span>|  
|<span data-ttu-id="cb2b7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="cb2b7-110">Channel</span></span>|<span data-ttu-id="cb2b7-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="cb2b7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cb2b7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb2b7-112">Description</span></span>  

 <span data-ttu-id="cb2b7-113">Esse evento é emitido depois que o modelo de serviço invoca o `AfterReceive` método em um inspetor de mensagem.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cb2b7-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="cb2b7-114">Message</span></span>  

 <span data-ttu-id="cb2b7-115">O Dispatcher invocou ' AfterReceiveReply ' em um MessageInspector do tipo ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cb2b7-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cb2b7-116">Details</span></span>  
  
|<span data-ttu-id="cb2b7-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="cb2b7-117">Data Item Name</span></span>|<span data-ttu-id="cb2b7-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="cb2b7-118">Data Item Type</span></span>|<span data-ttu-id="cb2b7-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb2b7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cb2b7-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="cb2b7-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="cb2b7-121">O CLR FullName do tipo do chamado `MessageInspector` .</span><span class="sxs-lookup"><span data-stu-id="cb2b7-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="cb2b7-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="cb2b7-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="cb2b7-123">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cb2b7-124">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cb2b7-125">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cb2b7-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cb2b7-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cb2b7-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cb2b7-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
