---
title: Método ICorProfilerCallback::JITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: 98e81d2d02a9495b678d49fb916f99068dd604f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725528"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>Método ICorProfilerCallback::JITCompilationFinished

Notifica o criador de perfil de que o compilador JIT (just-in-time) concluiu a compilação de uma função.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parâmetros

- `functionId`

  \[in] a ID da função que foi compilada.

- `hrStatus`

  \[in] um valor que indica se A compilação foi bem-sucedida.

- `fIsSafeToBlock`

  \[in] um valor que indica ao criador de perfil se o bloqueio afetará a operação do tempo de execução. O valor é `true` se o bloqueio pode fazer com que o tempo de execução aguarde o thread de chamada retornar desse retorno de chamada; caso contrário, `false` .

  Embora um valor de `true` não danifique o tempo de execução, ele pode distorcer os resultados de criação de perfil.

## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorProf. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorProfilerCallback](icorprofilercallback-interface.md)
- [Método JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
