---
title: Método ICorDebugController::IsRunning
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
ms.openlocfilehash: 73ed86ee12b02d292dc6dfc1d652459a679f81ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679930"
---
# <a name="icordebugcontrollerisrunning-method"></a>Método ICorDebugController::IsRunning

Obtém um valor que indica se os threads no processo estão em execução livremente no momento.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pbRunning`  
 fora Um ponteiro para um valor que `true` se os threads no processo estiverem em execução livremente; caso contrário, `false` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também
