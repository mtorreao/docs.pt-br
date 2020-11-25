---
title: Interface IReferenceAppId
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
ms.openlocfilehash: 9aa7173d81d84d9080d90b0890769ffeaee6a738
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728609"
---
# <a name="ireferenceappid-interface"></a>Interface IReferenceAppId

Representa uma referência ao identificador exclusivo para o aplicativo no escopo atual.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Obtém um ponteiro para uma representação de cadeia de caracteres do identificador de código para o aplicativo referenciado por isso `IReferenceAppId` .|  
|`IReferenceAppId::put_CodeBase`|Define o identificador de código para o aplicativo referenciado por isso `IReferenceAppId` .|  
|`IReferenceAppId::EnumAppPath`|Obtém um ponteiro de interface para uma `IEnumReferenceIdentity` instância que contém as `IReferenceIdentity` instâncias que representam os membros desse `IReferenceAppId` .|  
|`IReferenceAppId::get_SubscriptionId`|Obtém um ponteiro para uma representação de cadeia de caracteres do identificador de token para uma assinatura para isso `IReferenceAppId` .|  
|`IReferenceAppId::put_SubscriptionId`|Define o identificador de token para uma assinatura para `IReferenceAppId` o valor da cadeia de caracteres especificada.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Isolamento. h  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de fusão](fusion-interfaces.md)
- [Interface IEnumReferenceIdentity](ienumreferenceidentity-interface.md)
- [Interface IReferenceIdentity](ireferenceidentity-interface.md)
