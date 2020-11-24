---
title: Método ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 1cb9729f175a2e82e88386b0694467c6fe05636a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684442"
---
# <a name="icordebugtypegetclass-method"></a>Método ICorDebugType::GetClass

Obtém um ponteiro de interface para um ICorDebugClass que representa o tipo genérico não instanciado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppClass`  
 fora Um ponteiro para o endereço de uma `ICorDebugClass` interface que representa o tipo genérico não instanciado.  
  
## <a name="remarks"></a>Comentários  

 `GetClass` pode ser chamado somente sob determinadas condições. Chame [ICorDebugType:: GetType](icordebugtype-gettype-method.md) antes de chamar `GetClass` . Se `ICorDebugType::GetType` retorna um valor de CorElementType que é ELEMENT_TYPE_CLASS ou ELEMENT_TYPE_VALUETYPE, `GetClass` pode ser chamado para obter o tipo não instanciado para um tipo genérico.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
