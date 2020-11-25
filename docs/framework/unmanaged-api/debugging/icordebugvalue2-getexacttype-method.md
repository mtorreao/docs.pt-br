---
title: Método ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720354"
---
# <a name="icordebugvalue2getexacttype-method"></a>Método ICorDebugValue2::GetExactType

Obtém um ponteiro de interface para um objeto "ICorDebugType" que representa o <xref:System.Type> desse valor.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppType`  
 fora Um ponteiro para o endereço de um `ICorDebugType` objeto que representa o <xref:System.Type> do valor representado por esse objeto "ICorDebugValue2".  
  
## <a name="remarks"></a>Comentários  

 O método com reconhecimento de genéricos `GetExactType` substitui os métodos [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) e [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , sendo que cada um retorna informações sobre o tipo de um valor.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também
