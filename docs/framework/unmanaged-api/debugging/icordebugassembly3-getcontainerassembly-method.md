---
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 51e68e73983425cdd7d648b6856809fcba590f70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688543"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>Método ICorDebugAssembly3::GetContainerAssembly

Retorna o assembly do contêiner desse objeto `ICorDebugAssembly3`.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppAssembly`  
 Um ponteiro para o endereço de um objeto ICorDebugAssembly que representa o assembly do contêiner ou **nulo** se a chamada do método falhar.  
  
## <a name="return-value"></a>Valor Retornado  

 `S_OK` se a chamada do método for concluída com sucesso; caso contrário, `S_FALSE` , e `ppAssembly` será **nulo**.  
  
## <a name="remarks"></a>Comentários  

 Se esse assembly foi mesclado com outros dentro de um assembly de contêiner único, esse método retorna o assembly do contêiner. Para obter mais informações e terminologia, consulte o tópico [ICorDebugProcess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugAssembly3](icordebugassembly3-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
