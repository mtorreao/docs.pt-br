---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: 7027b6557520a9ccb587f8d383d3598571da5838
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279058"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="a4277-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="a4277-102">211 - ParameterInspectorAfterCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="a4277-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a4277-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a4277-104">ID</span><span class="sxs-lookup"><span data-stu-id="a4277-104">ID</span></span>|<span data-ttu-id="a4277-105">211</span><span class="sxs-lookup"><span data-stu-id="a4277-105">211</span></span>|  
|<span data-ttu-id="a4277-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="a4277-106">Keywords</span></span>|<span data-ttu-id="a4277-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a4277-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a4277-108">Nível</span><span class="sxs-lookup"><span data-stu-id="a4277-108">Level</span></span>|<span data-ttu-id="a4277-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="a4277-109">Information</span></span>|  
|<span data-ttu-id="a4277-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a4277-110">Channel</span></span>|<span data-ttu-id="a4277-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="a4277-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a4277-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4277-112">Description</span></span>  

 <span data-ttu-id="a4277-113">Esse evento é emitido depois que o modelo de serviço invoca o `AfterCall` método em um `ParameterInspector` .</span><span class="sxs-lookup"><span data-stu-id="a4277-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a4277-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="a4277-114">Message</span></span>  

 <span data-ttu-id="a4277-115">O Dispatcher invocou ' AfterCall ' em um ParameterInspector do tipo ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="a4277-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a4277-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a4277-116">Details</span></span>  
  
|<span data-ttu-id="a4277-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="a4277-117">Data Item Name</span></span>|<span data-ttu-id="a4277-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="a4277-118">Data Item Type</span></span>|<span data-ttu-id="a4277-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4277-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a4277-120">Nome do Tipo</span><span class="sxs-lookup"><span data-stu-id="a4277-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="a4277-121">O CLR FullName do tipo do chamado `ParameterInspector` .</span><span class="sxs-lookup"><span data-stu-id="a4277-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="a4277-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="a4277-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="a4277-123">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="a4277-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a4277-124">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="a4277-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a4277-125">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="a4277-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a4277-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a4277-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a4277-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a4277-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
