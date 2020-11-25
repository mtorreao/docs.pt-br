---
title: Interface ICLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: e23675351e1fd0de510243c9ee8b3a6dd6f29cec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714114"
---
# <a name="iclriocompletionmanager-interface"></a>Interface ICLRIoCompletionManager

Implementa um método de retorno de chamada que permite ao host notificar o Common Language Runtime (CLR) do status de solicitações de e/s especificadas.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método OnComplete](iclriocompletionmanager-oncomplete-method.md)|Notifica o CLR sobre o status de uma solicitação de e/s que foi feita usando uma chamada para o método [IHostIoCompletionManager:: bind](ihostiocompletionmanager-bind-method.md) .|  
  
## <a name="remarks"></a>Comentários  

 O host implementa a abstração de conclusão de e/s usando a interface [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) . O CLR faz solicitações de e/s por meio dessa interface, e o host notifica o tempo de execução do resultado de tais solicitações usando a `ICLRIoCompletionManager` interface.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IHostIoCompletionManager](ihostiocompletionmanager-interface.md)
- [Interface IHostThreadPoolManager](ihostthreadpoolmanager-interface.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
