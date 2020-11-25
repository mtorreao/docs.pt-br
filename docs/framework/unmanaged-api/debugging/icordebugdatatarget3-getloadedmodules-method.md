---
title: Método ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: efbada02b7a24e0a7ed613b86b8a4a1a0b5b051a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713737"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a>Método ICorDebugDataTarget3::GetLoadedModules

Obtém uma lista dos módulos que foram carregados até agora.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `cRequestedModules`  
 no O número de módulos para os quais as informações são solicitadas.  
  
 `pcFetchedModules`  
 fora Um ponteiro para o número de módulos sobre os quais as informações foram retornadas.  
  
 `pLoadedModules`  
 fora Um ponteiro para uma matriz de objetos [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) que fornecem informações sobre os módulos carregados.  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugDataTarget3](icordebugdatatarget3-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
