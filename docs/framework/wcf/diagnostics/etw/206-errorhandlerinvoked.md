---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 99415733624752217d32f6f026a419b2b32bfa7b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244607"
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="f3a00-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="f3a00-102">206 - ErrorHandlerInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="f3a00-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="f3a00-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3a00-104">ID</span><span class="sxs-lookup"><span data-stu-id="f3a00-104">ID</span></span>|<span data-ttu-id="f3a00-105">206</span><span class="sxs-lookup"><span data-stu-id="f3a00-105">206</span></span>|  
|<span data-ttu-id="f3a00-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="f3a00-106">Keywords</span></span>|<span data-ttu-id="f3a00-107">Solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f3a00-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f3a00-108">Nível</span><span class="sxs-lookup"><span data-stu-id="f3a00-108">Level</span></span>|<span data-ttu-id="f3a00-109">Informações do</span><span class="sxs-lookup"><span data-stu-id="f3a00-109">Information</span></span>|  
|<span data-ttu-id="f3a00-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f3a00-110">Channel</span></span>|<span data-ttu-id="f3a00-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="f3a00-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f3a00-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3a00-112">Description</span></span>  

 <span data-ttu-id="f3a00-113">Esse evento é emitido após uma `ErrorHandler` oportunidade de lidar com uma exceção que ocorreu em uma operação de serviço.</span><span class="sxs-lookup"><span data-stu-id="f3a00-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f3a00-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f3a00-114">Message</span></span>  

 <span data-ttu-id="f3a00-115">O Dispatcher invocou um ErrorHandler do tipo ' %1 ' com uma exceção do tipo ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="f3a00-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="f3a00-116">ErrorHandled = = ' %2 '.</span><span class="sxs-lookup"><span data-stu-id="f3a00-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f3a00-117">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f3a00-117">Details</span></span>  
  
|<span data-ttu-id="f3a00-118">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="f3a00-118">Data Item Name</span></span>|<span data-ttu-id="f3a00-119">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="f3a00-119">Data Item Type</span></span>|<span data-ttu-id="f3a00-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3a00-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f3a00-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="f3a00-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="f3a00-122">O CLR FullName do tipo do chamado `ErrorHandler` .</span><span class="sxs-lookup"><span data-stu-id="f3a00-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="f3a00-123">Manipulado</span><span class="sxs-lookup"><span data-stu-id="f3a00-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="f3a00-124">`true` Se o manipulador de erros tratou o erro, caso contrário `false` .</span><span class="sxs-lookup"><span data-stu-id="f3a00-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="f3a00-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="f3a00-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="f3a00-126">O CLR FullName da exceção que estava sendo tratada.</span><span class="sxs-lookup"><span data-stu-id="f3a00-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="f3a00-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="f3a00-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="f3a00-128">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="f3a00-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f3a00-129">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="f3a00-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f3a00-130">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="f3a00-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f3a00-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f3a00-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f3a00-132">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f3a00-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
