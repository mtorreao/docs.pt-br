---
title: Método ICorDebugProcess::ClearCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 0d36390a905561b64b3ca6ca95722f82158450be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695212"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>Método ICorDebugProcess::ClearCurrentException

Limpa a exceção não gerenciada atual no thread determinado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `threadID`  
 no A ID do thread no qual a exceção não gerenciada atual será apagada.  
  
## <a name="remarks"></a>Comentários  

 Chame esse método antes de chamar [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) quando um thread reportou uma exceção não gerenciada que deve ser ignorada pelo depurador. Isso limpará os eventos da IB (entrada em banda) e do OOB (fora de banda) no thread determinado. Todos os pontos de interrupção OOB e as exceções de etapa única são automaticamente apagados.  
  
 Use [ICorDebugThread2:: InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) para interceptar a exceção gerenciada atual em um thread.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
