---
title: Interface ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: c280852d421742cf9e8c2f8dcaa9c0f588f8537b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697383"
---
# <a name="icordebugexceptiondebugevent-interface"></a>Interface ICorDebugExceptionDebugEvent

Estende a interface [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para dar suporte a eventos de exceção.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetFlags](icordebugexceptiondebugevent-getflags-method.md)|Obtém um sinalizador que indica se a exceção pode ser interceptada.|  
|[Método GetNativeIP](icordebugexceptiondebugevent-getnativeip-method.md)|Obtém o ponteiro de interface nativa para este evento de depuração de exceção.|  
|[Método GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md)|Obtém o ponteiro de pilha para este evento de depuração de exceção.|  
  
## <a name="remarks"></a>Comentários  

 A `ICorDebugExceptionDebugEvent` interface é implementada pelos seguintes tipos de evento:  
  
- [MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> A interface está disponível somente com .NET Native. A tentativa de chamar `QueryInterface` para recuperar um ponteiro de interface retorna `E_NOINTERFACE` para cenários ICorDebug fora do .net Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
