---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 50a9424f445781cac70d7d7fde58beea10231cfa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267748"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="44f6b-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="44f6b-102">209 - MessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="44f6b-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="44f6b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44f6b-104">ID</span><span class="sxs-lookup"><span data-stu-id="44f6b-104">ID</span></span>|<span data-ttu-id="44f6b-105">209</span><span class="sxs-lookup"><span data-stu-id="44f6b-105">209</span></span>|  
|<span data-ttu-id="44f6b-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="44f6b-106">Keywords</span></span>|<span data-ttu-id="44f6b-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="44f6b-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="44f6b-108">Nível</span><span class="sxs-lookup"><span data-stu-id="44f6b-108">Level</span></span>|<span data-ttu-id="44f6b-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="44f6b-109">Information</span></span>|  
|<span data-ttu-id="44f6b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="44f6b-110">Channel</span></span>|<span data-ttu-id="44f6b-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="44f6b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="44f6b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="44f6b-112">Description</span></span>  

 <span data-ttu-id="44f6b-113">Esse evento é emitido depois que o modelo de serviço invoca o `BeforeSend` método em um inspetor de mensagem.</span><span class="sxs-lookup"><span data-stu-id="44f6b-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="44f6b-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="44f6b-114">Message</span></span>  

 <span data-ttu-id="44f6b-115">O Dispatcher invocou ' BeforeSendRequest ' em um MessageInspector do tipo ' %1 '.</span><span class="sxs-lookup"><span data-stu-id="44f6b-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="44f6b-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="44f6b-116">Details</span></span>  
  
|<span data-ttu-id="44f6b-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="44f6b-117">Data Item Name</span></span>|<span data-ttu-id="44f6b-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="44f6b-118">Data Item Type</span></span>|<span data-ttu-id="44f6b-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="44f6b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="44f6b-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="44f6b-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="44f6b-121">O CLR FullName do tipo do chamado `MessageInspector` .</span><span class="sxs-lookup"><span data-stu-id="44f6b-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="44f6b-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="44f6b-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="44f6b-123">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="44f6b-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="44f6b-124">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="44f6b-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="44f6b-125">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="44f6b-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="44f6b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="44f6b-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="44f6b-127">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="44f6b-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
