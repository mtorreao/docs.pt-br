---
title: Método ICorProfilerCallback::JITCachedFunctionSearchFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: fe07270989df897c3dbf689305784f9f0af65742
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684038"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>Método ICorProfilerCallback::JITCachedFunctionSearchFinished

Notifica o criador de perfil de que uma pesquisa foi concluída para uma função que foi compilada anteriormente usando o gerador de imagem nativa (NGen.exe).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a>Parâmetros

- `functionId`

  \[in] a ID da função para a qual a pesquisa foi executada.

- `result`

  \[in] um valor da enumeração [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) que indica o resultado da pesquisa.

## <a name="remarks"></a>Comentários  

 No .NET Framework versão 2,0, [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) e `JITCachedFunctionSearchFinished` retornos de chamada não serão feitos para todas as funções em imagens NGen regulares. Somente imagens NGen otimizadas para um criador de perfil gerarão retornos de chamada para todas as funções na imagem. No entanto, devido à sobrecarga adicional, um criador de perfil deve solicitar imagens NGen otimizadas para o criador de perfil somente se pretender usar esses retornos de chamada para forçar uma função a ser compilada just-in-time (JIT). Caso contrário, o criador de perfil deve usar uma estratégia lenta para coletar informações de função.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorProf. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorProfilerCallback](icorprofilercallback-interface.md)
