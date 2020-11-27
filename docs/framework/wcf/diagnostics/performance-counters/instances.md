---
title: Instâncias
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: f4bf639e626945c7e753ac352dfecc7a79541bfd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266071"
---
# <a name="instances"></a><span data-ttu-id="4ef23-102">Instâncias</span><span class="sxs-lookup"><span data-stu-id="4ef23-102">Instances</span></span>

<span data-ttu-id="4ef23-103">Nome do contador: instâncias.</span><span class="sxs-lookup"><span data-stu-id="4ef23-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4ef23-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="4ef23-104">Description</span></span>  

 <span data-ttu-id="4ef23-105">Número de contextos de instância que o serviço contém atualmente.</span><span class="sxs-lookup"><span data-stu-id="4ef23-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="4ef23-106">Na maioria das vezes, o número de contextos de instância é idêntico ao número de instâncias.</span><span class="sxs-lookup"><span data-stu-id="4ef23-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="4ef23-107">No entanto, os cenários a seguir são uma exceção a essa regra.</span><span class="sxs-lookup"><span data-stu-id="4ef23-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="4ef23-108">Um método de serviço chama o <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> método explicitamente.</span><span class="sxs-lookup"><span data-stu-id="4ef23-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="4ef23-109">Um <xref:System.ServiceModel.ReleaseInstanceMode> é aplicado a uma <xref:System.ServiceModel.OperationBehaviorAttribute> instância do.</span><span class="sxs-lookup"><span data-stu-id="4ef23-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef23-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="4ef23-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
