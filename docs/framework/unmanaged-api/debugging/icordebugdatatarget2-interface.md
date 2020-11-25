---
title: Interface ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: aa1db39b564b987fb8d0f79d529f5af59b7e4c02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713738"
---
# <a name="icordebugdatatarget2-interface"></a>Interface ICorDebugDataTarget2

Estende logicamente a interface [ICorDebugDataTarget](icordebugdatatarget-interface.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método CreateVirtualUnwinder](icordebugdatatarget2-createvirtualunwinder-method.md)|Cria um novo unwinder de pilha que inicia o desenrolamento de um contexto inicial (que não é necessariamente folha de um thread).|  
|[Método EnumerateThreadIDs](icordebugdatatarget2-enumeratethreadids-method.md)|Retorna uma lista de IDs de thread ativo.|  
|[Método GetImageFromPointer](icordebugdatatarget2-getimagefrompointer-method.md)|Retorna o endereço base do módulo e o tamanho de um endereço no módulo.|  
|[Método GetImageLocation](icordebugdatatarget2-getimagelocation-method.md)|Retorna o caminho de um módulo de endereço base do módulo.|  
|[Método GetSymbolProviderForImage](icordebugdatatarget2-getsymbolproviderforimage-method.md)|Retorna o provedor de símbolo para um módulo do endereço base do módulo.|  
  
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
