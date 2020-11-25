---
title: Método ICorProfilerCallback::ExceptionSearchFunctionLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
ms.openlocfilehash: 064f87fe0cee8d0ad7efcba478e9cf1954a3f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699749"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="9b273-102">Método ICorProfilerCallback::ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="9b273-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>

<span data-ttu-id="9b273-103">Notifica o criador de perfil de que a fase de pesquisa do tratamento de exceções concluiu a pesquisa de uma função.</span><span class="sxs-lookup"><span data-stu-id="9b273-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b273-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9b273-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="9b273-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b273-105">Requirements</span></span>  

 <span data-ttu-id="9b273-106">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b273-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b273-107">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="9b273-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b273-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b273-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b273-109">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b273-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b273-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="9b273-110">See also</span></span>

- [<span data-ttu-id="9b273-111">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9b273-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9b273-112">Método ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="9b273-112">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)
