---
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 71381c9eee6aed4792500c8558db88e239bf89f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295165"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="97c85-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="97c85-102">207 - FaultProviderInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="97c85-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="97c85-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97c85-104">ID</span><span class="sxs-lookup"><span data-stu-id="97c85-104">ID</span></span>|<span data-ttu-id="97c85-105">207</span><span class="sxs-lookup"><span data-stu-id="97c85-105">207</span></span>|  
|<span data-ttu-id="97c85-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="97c85-106">Keywords</span></span>|<span data-ttu-id="97c85-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="97c85-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="97c85-108">Nível</span><span class="sxs-lookup"><span data-stu-id="97c85-108">Level</span></span>|<span data-ttu-id="97c85-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="97c85-109">Information</span></span>|  
|<span data-ttu-id="97c85-110">Canal</span><span class="sxs-lookup"><span data-stu-id="97c85-110">Channel</span></span>|<span data-ttu-id="97c85-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="97c85-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="97c85-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="97c85-112">Description</span></span>  

 <span data-ttu-id="97c85-113">Esse evento é emitido depois que um `FaultProvider` é invocado.</span><span class="sxs-lookup"><span data-stu-id="97c85-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="97c85-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="97c85-114">Message</span></span>  

 <span data-ttu-id="97c85-115">O Dispatcher invocou um Faultprovider do tipo ' %1 ' com uma exceção do tipo ' %2 '.</span><span class="sxs-lookup"><span data-stu-id="97c85-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="97c85-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="97c85-116">Details</span></span>  
  
|<span data-ttu-id="97c85-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="97c85-117">Data Item Name</span></span>|<span data-ttu-id="97c85-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="97c85-118">Data Item Type</span></span>|<span data-ttu-id="97c85-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="97c85-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="97c85-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="97c85-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="97c85-121">O CLR FullName do tipo do chamado `FaultProvider` .</span><span class="sxs-lookup"><span data-stu-id="97c85-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="97c85-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="97c85-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="97c85-123">O CLR FullName da exceção em que o `FaultProvider` foi operado.</span><span class="sxs-lookup"><span data-stu-id="97c85-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="97c85-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="97c85-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="97c85-125">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="97c85-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="97c85-126">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="97c85-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="97c85-127">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="97c85-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="97c85-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="97c85-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="97c85-129">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="97c85-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
