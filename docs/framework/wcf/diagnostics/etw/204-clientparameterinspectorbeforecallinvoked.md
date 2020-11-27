---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
ms.openlocfilehash: a7db8c9fa87518c59969f3089ff033fa8c912577
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275782"
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="a6f00-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="a6f00-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="a6f00-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a6f00-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6f00-104">ID</span><span class="sxs-lookup"><span data-stu-id="a6f00-104">ID</span></span>|<span data-ttu-id="a6f00-105">204</span><span class="sxs-lookup"><span data-stu-id="a6f00-105">204</span></span>|  
|<span data-ttu-id="a6f00-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a6f00-106">Keywords</span></span>|<span data-ttu-id="a6f00-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a6f00-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a6f00-108">Nível</span><span class="sxs-lookup"><span data-stu-id="a6f00-108">Level</span></span>|<span data-ttu-id="a6f00-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="a6f00-109">Information</span></span>|  
|<span data-ttu-id="a6f00-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a6f00-110">Channel</span></span>|<span data-ttu-id="a6f00-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="a6f00-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6f00-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a6f00-112">Description</span></span>  

 <span data-ttu-id="a6f00-113">Esse evento é emitido depois que o modelo de serviço invoca o `BeforeCall` método em um inspetor de parâmetro do cliente.</span><span class="sxs-lookup"><span data-stu-id="a6f00-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6f00-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="a6f00-114">Message</span></span>  

 <span data-ttu-id="a6f00-115">O Dispatcher invocou ' BeforeCall ' em um ClientParameterInspector do tipo ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="a6f00-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6f00-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a6f00-116">Details</span></span>  
  
|<span data-ttu-id="a6f00-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="a6f00-117">Data Item Name</span></span>|<span data-ttu-id="a6f00-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="a6f00-118">Data Item Type</span></span>|<span data-ttu-id="a6f00-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="a6f00-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6f00-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="a6f00-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="a6f00-121">O CLR FullName do tipo do Inspetor invocado.</span><span class="sxs-lookup"><span data-stu-id="a6f00-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="a6f00-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="a6f00-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="a6f00-123">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="a6f00-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a6f00-124">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="a6f00-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a6f00-125">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="a6f00-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a6f00-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a6f00-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a6f00-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a6f00-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
