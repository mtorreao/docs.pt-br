---
title: Método ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
ms.openlocfilehash: d9150d15ac183b65b87448424f265693ed7b7ab7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726568"
---
# <a name="icordebugheapvalueisvalid-method"></a>Método ICorDebugHeapValue::IsValid

Obtém um valor que indica se o objeto representado por este ICorDebugHeapValue é válido.  
  
 Esse método foi preterido no .NET Framework versão 2,0.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pbValid`  
 fora Um ponteiro para um valor booliano que indica se esse valor no heap é válido.  
  
## <a name="remarks"></a>Comentários  

 O valor será inválido se tiver sido recuperado pelo coletor de lixo.  
  
 Esse método foi substituído. No .NET Framework 2,0, todos os valores são válidos até que [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) seja chamado e, nesse momento, os valores são invalidados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
