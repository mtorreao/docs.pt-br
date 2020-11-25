---
title: Método ICorDebugObjectValue::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: 42e5ffeeb81bc5e9a99c8ada8d58296fc9f610d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695394"
---
# <a name="icordebugobjectvaluegetclass-method"></a>Método ICorDebugObjectValue::GetClass

Obtém a classe desse valor de objeto.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppClass`  
 fora Um ponteiro para o endereço de um objeto "ICorDebugClass" que representa a classe do valor do objeto representado por esse objeto "ICorDebugObjectValue".  
  
## <a name="remarks"></a>Comentários  

 Os `GetClass` métodos e [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) retornam informações sobre o tipo de um valor; eles são ambos substituídos pelo [ICorDebugValue2:: getexatotype](icordebugvalue2-getexacttype-method.md)com reconhecimento de genéricos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também
