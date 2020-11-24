---
title: Interface ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 67f2234d37165e421874815bdc2ef34f8f50749a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679371"
---
# <a name="icordebugvirtualunwinder-interface"></a>Interface ICorDebugVirtualUnwinder

Fornece métodos para ajudar no desenrolamento de pilha.  
  
## <a name="methods"></a>Métodos  
  
|Método|Nome|  
|------------|----------|  
|[Método GetContext](icordebugvirtualunwinder-getcontext-method.md)|Obtém o contexto atual deste desenrolador.|  
|[Método Next](icordebugvirtualunwinder-next-method.md)|Avança para o contexto do chamador.|  
  
## <a name="remarks"></a>Comentários  

 Os membros da `ICorDebugVirtualUnwinder` interface são implementados pelo depurador para ajudar no desenrolamento da pilha.  
  
> [!NOTE]
> Essa interface está disponível somente com .NET Native. Se você implementar essa interface para cenários ICorDebug fora do .NET Native, o Common Language Runtime ignorará essa interface.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
