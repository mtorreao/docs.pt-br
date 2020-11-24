---
title: Método ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: d8375948be5820aaf6e879b82bcfde6471cccf3f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679891"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>Método ICorDebugController::SetAllThreadsDebugState

Define o estado de depuração de todos os threads gerenciados no processo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `state`  
 no Um valor da enumeração "CorDebugThreadState" que especifica o estado do thread para depuração.  
  
 `pExceptThisThread`  
 no Um ponteiro para um objeto "ICorDebugThread" que representa um thread a ser isento da configuração de estado de depuração. Se esse valor for NULL, nenhum thread será isento.  
  
## <a name="remarks"></a>Comentários  

 O `SetAllThreadsDebugState` método pode afetar os threads que não são visíveis por meio do [método EnumerateThreads](icordebugcontroller-enumeratethreads-method.md), de modo que os threads que foram suspensos com o `SetAllThreadsDebugState` método precisarão ser retomados com o `SetAllThreadsDebugState` método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também
