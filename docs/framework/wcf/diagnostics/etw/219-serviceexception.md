---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241935"
---
# <a name="219---serviceexception"></a><span data-ttu-id="c220e-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="c220e-102">219 - ServiceException</span></span>

## <a name="properties"></a><span data-ttu-id="c220e-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="c220e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c220e-104">ID</span><span class="sxs-lookup"><span data-stu-id="c220e-104">ID</span></span>|<span data-ttu-id="c220e-105">219</span><span class="sxs-lookup"><span data-stu-id="c220e-105">219</span></span>|  
|<span data-ttu-id="c220e-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="c220e-106">Keywords</span></span>|<span data-ttu-id="c220e-107">EndToEndMonitoring, HealthMonitoring, solução de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c220e-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="c220e-108">Nível</span><span class="sxs-lookup"><span data-stu-id="c220e-108">Level</span></span>|<span data-ttu-id="c220e-109">Erro do</span><span class="sxs-lookup"><span data-stu-id="c220e-109">Error</span></span>|  
|<span data-ttu-id="c220e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c220e-110">Channel</span></span>|<span data-ttu-id="c220e-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="c220e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c220e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c220e-112">Description</span></span>  

 <span data-ttu-id="c220e-113">Esse evento é emitido quando um serviço WCF encontra uma exceção sem tratamento.</span><span class="sxs-lookup"><span data-stu-id="c220e-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="c220e-114">Isso inclui exceções sem tratamento durante a ativação, durante o processamento da mensagem e no código do usuário.</span><span class="sxs-lookup"><span data-stu-id="c220e-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c220e-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="c220e-115">Message</span></span>  

 <span data-ttu-id="c220e-116">Houve uma exceção sem tratamento do tipo ' %2 ' durante o processamento da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c220e-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="c220e-117">Exceção ToString completa: %1.</span><span class="sxs-lookup"><span data-stu-id="c220e-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c220e-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c220e-118">Details</span></span>  
  
|<span data-ttu-id="c220e-119">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="c220e-119">Data Item Name</span></span>|<span data-ttu-id="c220e-120">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="c220e-120">Data Item Type</span></span>|<span data-ttu-id="c220e-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="c220e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c220e-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="c220e-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="c220e-123">O resultado de chamada `ToString` () na exceção CLR.</span><span class="sxs-lookup"><span data-stu-id="c220e-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="c220e-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="c220e-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="c220e-125">O CLR FullName do tipo da exceção.</span><span class="sxs-lookup"><span data-stu-id="c220e-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="c220e-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="c220e-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="c220e-127">Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web.</span><span class="sxs-lookup"><span data-stu-id="c220e-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="c220e-128">Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="c220e-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="c220e-129">Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="c220e-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="c220e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c220e-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c220e-131">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c220e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
