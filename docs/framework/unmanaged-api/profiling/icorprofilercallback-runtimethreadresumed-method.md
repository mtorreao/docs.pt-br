---
title: Método ICorProfilerCallback::RuntimeThreadResumed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
ms.openlocfilehash: 0996d7eb5b7354a67106ec7aa8818d5e4d46232e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717213"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="82faf-102">Método ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="82faf-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>

<span data-ttu-id="82faf-103">Notifica o criador de perfil de que o thread especificado foi retomado após ser suspenso.</span><span class="sxs-lookup"><span data-stu-id="82faf-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82faf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="82faf-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82faf-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="82faf-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="82faf-106">no A ID do thread que foi retomado.</span><span class="sxs-lookup"><span data-stu-id="82faf-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82faf-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82faf-107">Requirements</span></span>  

 <span data-ttu-id="82faf-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82faf-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82faf-109">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="82faf-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82faf-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82faf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82faf-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82faf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82faf-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="82faf-112">See also</span></span>

- [<span data-ttu-id="82faf-113">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="82faf-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="82faf-114">Método RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="82faf-114">RuntimeThreadSuspended Method</span></span>](icorprofilercallback-runtimethreadsuspended-method.md)
