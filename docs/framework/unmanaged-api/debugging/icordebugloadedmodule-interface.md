---
title: Interface ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 6087411e8d23a9c3c97cb97ac8159d436e24759b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731820"
---
# <a name="icordebugloadedmodule-interface"></a>Interface ICorDebugLoadedModule

Fornece informações sobre um módulo carregado.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetBaseAddress](icordebugloadedmodule-getbaseaddress-method.md)|Obtém o endereço base do módulo carregado.|  
|[Método GetName](icordebugloadedmodule-getname-method.md)|Obtém o nome do módulo carregado.|  
|[Método GetSize](icordebugloadedmodule-getsize-method.md)|Obtém o tamanho em bytes do módulo carregado.|  
  
## <a name="remarks"></a>Comentários  

 A `ICorDebugLoadedModule` interface é implementada por um depurador e é usada pelas interfaces de depuração CLR para obter informações sobre o módulo carregado do depurador.  
  
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
