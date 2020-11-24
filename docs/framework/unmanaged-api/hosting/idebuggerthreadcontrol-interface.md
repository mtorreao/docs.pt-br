---
title: Interface IDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
ms.openlocfilehash: 2268fce5d3ca732d852edfdb6f0edf63117df363
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684207"
---
# <a name="idebuggerthreadcontrol-interface"></a>Interface IDebuggerThreadControl

Fornece métodos para notificar o host sobre o bloqueio e o desbloqueio de threads pelos serviços de depuração.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método ThreadIsBlockingForDebugger](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|Notifica o host que o thread que está enviando esse retorno de chamada está prestes a ser bloqueado nos serviços de depuração.|  
|[Método ReleaseAllRuntimeThreads](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|Notifica o host de que os serviços de depuração estão prestes a liberar todos os threads bloqueados.|  
|[Método StartBlockingForDebugger](idebuggerthreadcontrol-startblockingfordebugger-method.md)|Notifica o host de que os serviços de depuração estão prestes a começar a bloquear todos os threads.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de hospedagem](hosting-interfaces.md)
