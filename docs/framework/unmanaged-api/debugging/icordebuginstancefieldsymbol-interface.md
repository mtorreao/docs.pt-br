---
title: Interface ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 4ef0f7a46acf7e9df732d630c9eb22044e09d658
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724891"
---
# <a name="icordebuginstancefieldsymbol-interface"></a>Interface ICorDebugInstanceFieldSymbol

Representa as informações de símbolo de depuração de um campo de instância.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetName](icordebuginstancefieldsymbol-getname-method.md)|Obtém o nome do campo de instância.|  
|[Método GetOffset](icordebuginstancefieldsymbol-getoffset-method.md)|Obtém o deslocamento em bytes deste campo de instância em sua classe pai.|  
|[Método GetSize](icordebuginstancefieldsymbol-getsize-method.md)|Obtém o tamanho em bytes do campo de instância.|  
  
## <a name="remarks"></a>Comentários  

 A `ICorDebugInstanceFieldSymbol` interface é usada para recuperar as informações de símbolo de depuração para um campo de instância.  
  
> [!NOTE]
> Essa interface está disponível somente com .NET Native. Se você implementar essa interface para cenários ICorDebug fora do .NET Native, o Common Language Runtime ignorará essa interface.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
