---
title: Método ICorProfilerCallback::RuntimeResumeFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: e7bd07205a87ecefb658e01db17100a48681b54b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732028"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="ebe45-102">Método ICorProfilerCallback::RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="ebe45-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>

<span data-ttu-id="ebe45-103">Notifica o criador de perfil de que o tempo de execução retomou todos os threads de tempo de execução e retornou à operação normal.</span><span class="sxs-lookup"><span data-stu-id="ebe45-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe45-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ebe45-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ebe45-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="ebe45-105">Remarks</span></span>  

 <span data-ttu-id="ebe45-106">`RuntimeResumeFinished`Não há garantia de que o retorno de chamada ocorra no mesmo thread que o retorno de chamada [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ebe45-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="ebe45-107">No entanto, é garantido que ocorra no mesmo thread que o retorno de chamada [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ebe45-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebe45-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebe45-108">Requirements</span></span>  

 <span data-ttu-id="ebe45-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebe45-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebe45-110">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="ebe45-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ebe45-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebe45-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebe45-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebe45-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe45-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="ebe45-113">See also</span></span>

- [<span data-ttu-id="ebe45-114">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ebe45-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
