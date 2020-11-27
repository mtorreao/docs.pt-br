---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: b964c26c9684cedef0fbe427bfd9ad232d199f12
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251523"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="1982e-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="1982e-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="1982e-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="1982e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1982e-104">ID</span><span class="sxs-lookup"><span data-stu-id="1982e-104">ID</span></span>|<span data-ttu-id="1982e-105">203</span><span class="sxs-lookup"><span data-stu-id="1982e-105">203</span></span>|  
|<span data-ttu-id="1982e-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="1982e-106">Keywords</span></span>|<span data-ttu-id="1982e-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1982e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1982e-108">Nível</span><span class="sxs-lookup"><span data-stu-id="1982e-108">Level</span></span>|<span data-ttu-id="1982e-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="1982e-109">Information</span></span>|  
|<span data-ttu-id="1982e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="1982e-110">Channel</span></span>|<span data-ttu-id="1982e-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="1982e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1982e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="1982e-112">Description</span></span>  

 <span data-ttu-id="1982e-113">Esse evento é emitido depois que o modelo de serviço invoca o `AfterCall` método em um inspetor de parâmetro do cliente.</span><span class="sxs-lookup"><span data-stu-id="1982e-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1982e-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="1982e-114">Message</span></span>  

 <span data-ttu-id="1982e-115">O Dispatcher invocou ' AfterCall ' em um ClientParameterInspector do tipo ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="1982e-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1982e-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1982e-116">Details</span></span>  
  
|<span data-ttu-id="1982e-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="1982e-117">Data Item Name</span></span>|<span data-ttu-id="1982e-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="1982e-118">Data Item Type</span></span>|<span data-ttu-id="1982e-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="1982e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1982e-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="1982e-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="1982e-121">O CLR FullName do tipo do Inspetor invocado.</span><span class="sxs-lookup"><span data-stu-id="1982e-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="1982e-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="1982e-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="1982e-123">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="1982e-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1982e-124">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="1982e-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1982e-125">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="1982e-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1982e-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1982e-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1982e-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1982e-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
