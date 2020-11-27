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
# <a name="instances"></a>Instâncias

Nome do contador: instâncias.  
  
## <a name="description"></a>Descrição  

 Número de contextos de instância que o serviço contém atualmente.  
  
 Na maioria das vezes, o número de contextos de instância é idêntico ao número de instâncias. No entanto, os cenários a seguir são uma exceção a essa regra.  
  
- Um método de serviço chama o <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> método explicitamente.  
  
- Um <xref:System.ServiceModel.ReleaseInstanceMode> é aplicado a uma <xref:System.ServiceModel.OperationBehaviorAttribute> instância do.  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.OperationBehaviorAttribute>
