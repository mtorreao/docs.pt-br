---
title: Interface ICorThreadpool
ms.date: 03/30/2017
api_name:
- ICorThreadpool
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorThreadpool
helpviewer_keywords:
- ICorThreadpool interface [.NET Framework hosting]
ms.assetid: 18485a27-cae3-4c6a-baa8-f7df601122d5
topic_type:
- apiref
ms.openlocfilehash: 2be1c5273a5450ce0f793ffa1fc10746e2f1161f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733939"
---
# <a name="icorthreadpool-interface"></a>Interface ICorThreadpool

Fornece métodos para acessar o pool de threads.  
  
> [!NOTE]
> Esta interface é reservada somente para uso interno.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método CorRegisterWaitForSingleObject](icorthreadpool-corregisterwaitforsingleobject-method.md)|Reservado apenas para uso interno.|  
|[Método CorUnregisterWait](icorthreadpool-corunregisterwait-method.md)|Reservado apenas para uso interno.|  
|[Método CorQueueUserWorkItem](icorthreadpool-corqueueuserworkitem-method.md)|Reservado apenas para uso interno.|  
|[Método CorCreateTimer](icorthreadpool-corcreatetimer-method.md)|Reservado apenas para uso interno.|  
|[Método CorChangeTimer](icorthreadpool-corchangetimer-method.md)|Reservado apenas para uso interno.|  
|[Método CorDeleteTimer](icorthreadpool-cordeletetimer-method.md)|Reservado apenas para uso interno.|  
|[Método CorBindIoCompletionCallback](icorthreadpool-corbindiocompletioncallback-method.md)|Reservado apenas para uso interno.|  
|[Método CorCallOrQueueUserWorkItem](icorthreadpool-corcallorqueueuserworkitem-method.md)|Reservado apenas para uso interno.|  
|[Método CorSetMaxThreads](icorthreadpool-corsetmaxthreads-method.md)|Reservado apenas para uso interno.|  
|[Método CorGetMaxThreads](icorthreadpool-corgetmaxthreads-method.md)|Reservado apenas para uso interno.|  
|[Método CorGetAvailableThreads](icorthreadpool-corgetavailablethreads-method.md)|Reservado apenas para uso interno.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de hospedagem](hosting-interfaces.md)
