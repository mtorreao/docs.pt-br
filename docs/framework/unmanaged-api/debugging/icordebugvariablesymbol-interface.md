---
title: Interface ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 3d808fd49eb7767f1f48ad4e07d8ba7e47c8f34b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679475"
---
# <a name="icordebugvariablesymbol-interface"></a>Interface ICorDebugVariableSymbol

Recupera as informações de símbolo de depuração para uma variável.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetName](icordebugvariablesymbol-getname-method.md)|Obtém o nome de uma variável.|  
|[Método GetSize](icordebugvariablesymbol-getsize-method.md)|Obtém o tamanho de uma variável em bytes.|  
|[Método GetSlotIndex](icordebugvariablesymbol-getslotindex-method.md)|Obtém o índice de slot gerenciado de uma variável local.|  
|[Método GetValue](icordebugvariablesymbol-getvalue-method.md)|Obtém o valor de uma variável como uma matriz de bytes.|  
|[Método SetValue](icordebugvariablesymbol-setvalue-method.md)|Atribui o valor de uma matriz de bytes a uma variável.|  
  
## <a name="remarks"></a>Comentários  
  
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
