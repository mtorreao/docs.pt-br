---
title: Método IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: 490648ab8883b1dba257b82c0d0fa3c8e4783814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684155"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a>Método IDebuggerThreadControl::ReleaseAllRuntimeThreads

Notifica o host de que os serviços de depuração estão prestes a liberar todos os threads bloqueados.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a>Comentários  

 O `ReleaseAllRuntimeThreads` método nunca será chamado em um thread de tempo de execução. Se o host tiver um thread de tempo de execução bloqueado, ele deverá liberá-lo agora.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IDebuggerThreadControl](idebuggerthreadcontrol-interface.md)
