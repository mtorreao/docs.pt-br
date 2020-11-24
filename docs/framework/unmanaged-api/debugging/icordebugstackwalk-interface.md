---
title: Interface ICorDebugStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: b37a89c0a86df49c894dc43676f8feafb80f5c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687509"
---
# <a name="icordebugstackwalk-interface"></a>Interface ICorDebugStackWalk

Fornece métodos para colocar os métodos gerenciados, ou quadros, em uma pilha de thread.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetContext](icordebugstackwalk-getcontext-method.md)|Retorna o contexto do quadro atual no `ICorDebugStackWalk` objeto.|  
|[Método SetContext](icordebugstackwalk-setcontext-method.md)|Define o `ICorDebugStackWalk` contexto atual do objeto como um contexto válido para o thread.|  
|[Método Next](icordebugstackwalk-next-method.md)|Move o `ICorDebugStackWalk` objeto para o próximo quadro.|  
|[Método GetFrame](icordebugstackwalk-getframe-method.md)|Obtém o quadro atual no `ICorDebugStackWalk` objeto.|  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
