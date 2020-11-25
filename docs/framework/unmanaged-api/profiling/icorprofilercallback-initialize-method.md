---
title: Método ICorProfilerCallback::Initialize
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: 26df1599af247bd08d3702d4ef3c5aa2f648620c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720367"
---
# <a name="icorprofilercallbackinitialize-method"></a>Método ICorProfilerCallback::Initialize

Chamado para inicializar o criador de perfil de código sempre que um novo aplicativo Common Language Runtime (CLR) é iniciado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parâmetros

- `pICorProfilerInfoUnk`

  \[in] ponteiro para uma interface [IUnknown](/cpp/atl/iunknown) que o criador de perfil deve consultar para um ponteiro de interface [ICorProfilerInfo](icorprofilerinfo-interface.md) .  

## <a name="remarks"></a>Comentários  

 A `Initialize` chamada é a única oportunidade para habilitar (ou desabilitar) retornos de chamada que são imutáveis. Depois que um retorno de chamada é habilitado pelo `Initialize` Call, ele não pode ser desabilitado posteriormente usando [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). O valor COR_PRF_MONITOR_IMMUTABLE da enumeração [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica quais eventos são imutáveis.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorProf. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorProfilerCallback](icorprofilercallback-interface.md)
- [Método Shutdown](icorprofilercallback-shutdown-method.md)
