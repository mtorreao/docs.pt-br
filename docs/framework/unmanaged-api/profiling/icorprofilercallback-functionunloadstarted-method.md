---
title: Método ICorProfilerCallback::FunctionUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: bab8d446347646081cee635035e954da58c3550c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733874"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="e357c-102">Método ICorProfilerCallback::FunctionUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="e357c-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>

<span data-ttu-id="e357c-103">Notifica o criador de perfil de que o tempo de execução começou a descarregar uma função.</span><span class="sxs-lookup"><span data-stu-id="e357c-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e357c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e357c-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="e357c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e357c-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="e357c-106">\[in] a ID da função que está sendo descarregada.</span><span class="sxs-lookup"><span data-stu-id="e357c-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="e357c-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="e357c-107">Remarks</span></span>  

 <span data-ttu-id="e357c-108">O valor do `functionId` parâmetro não é mais válido depois que esse método retorna ao chamador.</span><span class="sxs-lookup"><span data-stu-id="e357c-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e357c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e357c-109">Requirements</span></span>  

 <span data-ttu-id="e357c-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e357c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e357c-111">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="e357c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e357c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e357c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e357c-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e357c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e357c-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="e357c-114">See also</span></span>

- [<span data-ttu-id="e357c-115">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e357c-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
