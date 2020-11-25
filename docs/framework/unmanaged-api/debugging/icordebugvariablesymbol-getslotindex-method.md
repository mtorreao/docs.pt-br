---
title: 'Método ICorDebugVariableSymbol:: GetSlotIndex'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: fc42517cb95dfc14c472b5bb9111ebd70639cee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725983"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>Método ICorDebugVariableSymbol:: GetSlotIndex

Obtém o índice de slot gerenciado de uma variável local.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pSlotIndex`  
 fora Um ponteiro para o índice de slot da variável local.  
  
## <a name="return-value"></a>Valor Retornado  

 `S_OK` se bem-sucedido. `E_FAIL` se a variável for um argumento de função.  
  
## <a name="remarks"></a>Comentários  

 O índice de slot gerenciado de uma variável local pode ser usado para recuperar as informações de metadados da variável  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
