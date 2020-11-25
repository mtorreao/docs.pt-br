---
title: 'Método ICorDebugCode4:: EnumerateVariableHomes'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 6d58efa5629bb02158a275dec61c0313bca821a1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720744"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>Método ICorDebugCode4:: EnumerateVariableHomes

Obtém um enumerador para as variáveis locais e argumentos em uma função.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppEnum`  
 Um ponteiro para o endereço de um objeto de interface [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) que é um enumerador para as variáveis locais e argumentos em uma função.  
  
## <a name="remarks"></a>Comentários  

 O objeto de interface [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) é um enumerador padrão derivado da interface "ICorDebugEnum" que permite enumerar objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) . A coleção pode incluir vários objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) para o mesmo índice de slot ou de argumento se eles tiverem diferentes residências em pontos diferentes na função.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugCode4](icordebugcode4-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
