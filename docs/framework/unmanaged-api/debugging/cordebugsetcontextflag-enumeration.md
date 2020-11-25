---
title: Enumeração CorDebugSetContextFlag
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
ms.openlocfilehash: 078dfefc70704eaadb9cf3c06cfe58f276f7dfce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726009"
---
# <a name="cordebugsetcontextflag-enumeration"></a>Enumeração CorDebugSetContextFlag

Indica se o contexto é do quadro ativo (ou folha) na pilha ou se foi computado pelo desenrolamento de outro quadro.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|SET_CONTEXT_FLAG_ACTIVE_FRAME|O contexto é o contexto ativo do thread.|  
|SET_CONTEXT_FLAG_UNWIND_FRAME|O contexto foi calculado com o desenrolamento de outro quadro.|  
  
## <a name="remarks"></a>Comentários  

 `CorDebugSetContextFlag` Fornece valores que são usados pelo método [ICorDebugStackWalk:: SetContext](icordebugstackwalk-setcontext-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Declarando enumerações](debugging-enumerations.md)
- [Depuração](index.md)
