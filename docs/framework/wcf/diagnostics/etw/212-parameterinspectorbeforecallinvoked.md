---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 28c2aca4555d2e4ff498e450deae55ad6a87743c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279032"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="2b977-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="2b977-102">212 - ParameterInspectorBeforeCallInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="2b977-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="2b977-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b977-104">ID</span><span class="sxs-lookup"><span data-stu-id="2b977-104">ID</span></span>|<span data-ttu-id="2b977-105">212</span><span class="sxs-lookup"><span data-stu-id="2b977-105">212</span></span>|  
|<span data-ttu-id="2b977-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="2b977-106">Keywords</span></span>|<span data-ttu-id="2b977-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2b977-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2b977-108">Nível</span><span class="sxs-lookup"><span data-stu-id="2b977-108">Level</span></span>|<span data-ttu-id="2b977-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="2b977-109">Information</span></span>|  
|<span data-ttu-id="2b977-110">Canal</span><span class="sxs-lookup"><span data-stu-id="2b977-110">Channel</span></span>|<span data-ttu-id="2b977-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="2b977-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b977-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b977-112">Description</span></span>  

 <span data-ttu-id="2b977-113">Esse evento é emitido depois que o modelo de serviço invoca o `BeforeCall` método em um `ParameterInspector` .</span><span class="sxs-lookup"><span data-stu-id="2b977-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2b977-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="2b977-114">Message</span></span>  

 <span data-ttu-id="2b977-115">O Dispatcher invocou ' BeforeCall ' em um ParameterInspector do tipo ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="2b977-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2b977-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2b977-116">Details</span></span>  
  
|<span data-ttu-id="2b977-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="2b977-117">Data Item Name</span></span>|<span data-ttu-id="2b977-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="2b977-118">Data Item Type</span></span>|<span data-ttu-id="2b977-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="2b977-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2b977-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="2b977-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="2b977-121">O CLR FullName do tipo do Inspetor invocado.</span><span class="sxs-lookup"><span data-stu-id="2b977-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="2b977-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="2b977-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="2b977-123">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="2b977-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2b977-124">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="2b977-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2b977-125">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="2b977-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2b977-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2b977-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2b977-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2b977-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
