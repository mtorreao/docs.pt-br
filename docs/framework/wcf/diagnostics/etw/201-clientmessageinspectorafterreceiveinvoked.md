---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: d84f6c6f38868f7915caaaf87e15885099b65456
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266669"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="c7603-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="c7603-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="c7603-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="c7603-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7603-104">ID</span><span class="sxs-lookup"><span data-stu-id="c7603-104">ID</span></span>|<span data-ttu-id="c7603-105">201</span><span class="sxs-lookup"><span data-stu-id="c7603-105">201</span></span>|  
|<span data-ttu-id="c7603-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="c7603-106">Keywords</span></span>|<span data-ttu-id="c7603-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c7603-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="c7603-108">Nível</span><span class="sxs-lookup"><span data-stu-id="c7603-108">Level</span></span>|<span data-ttu-id="c7603-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="c7603-109">Information</span></span>|  
|<span data-ttu-id="c7603-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c7603-110">Channel</span></span>|<span data-ttu-id="c7603-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="c7603-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c7603-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7603-112">Description</span></span>  

 <span data-ttu-id="c7603-113">Esse evento é emitido depois que o modelo de serviço invoca o `AfterReceiveReply` método em um inspetor de mensagem do cliente.</span><span class="sxs-lookup"><span data-stu-id="c7603-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c7603-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="c7603-114">Message</span></span>  

 <span data-ttu-id="c7603-115">O Dispatcher invocou ' AfterReceiveReply ' em um ClientMessageInspector do tipo ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="c7603-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c7603-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c7603-116">Details</span></span>  
  
|<span data-ttu-id="c7603-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="c7603-117">Data Item Name</span></span>|<span data-ttu-id="c7603-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="c7603-118">Data Item Type</span></span>|<span data-ttu-id="c7603-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7603-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c7603-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="c7603-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="c7603-121">O CLR FullName do tipo do Inspetor invocado.</span><span class="sxs-lookup"><span data-stu-id="c7603-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="c7603-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="c7603-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="c7603-123">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="c7603-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="c7603-124">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="c7603-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="c7603-125">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="c7603-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="c7603-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c7603-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c7603-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c7603-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
