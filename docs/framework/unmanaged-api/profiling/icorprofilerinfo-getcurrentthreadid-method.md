---
title: Método ICorProfilerInfo::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: 18298c4c726d7d850e67afbf82ca77b7511d8917
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722577"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="e7f91-102">Método ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="e7f91-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>

<span data-ttu-id="e7f91-103">Obtém a ID do thread atual, se for um thread gerenciado.</span><span class="sxs-lookup"><span data-stu-id="e7f91-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f91-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e7f91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7f91-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e7f91-105">Parameters</span></span>  

 `pThreadId`  
 <span data-ttu-id="e7f91-106">fora Um ponteiro para a ID retornada do thread gerenciado.</span><span class="sxs-lookup"><span data-stu-id="e7f91-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7f91-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="e7f91-107">Remarks</span></span>  

 <span data-ttu-id="e7f91-108">Se o thread atual for um thread de tempo de execução interno ou outro thread não gerenciado, `GetCurrentThreadID` o retornará CORPROF_E_NOT_MANAGED_THREAD como HRESULT e o valor retornado do `pThreadId` parâmetro será NULL.</span><span class="sxs-lookup"><span data-stu-id="e7f91-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7f91-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7f91-109">Requirements</span></span>  

 <span data-ttu-id="e7f91-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7f91-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7f91-111">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="e7f91-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7f91-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7f91-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7f91-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7f91-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7f91-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="e7f91-114">See also</span></span>

- [<span data-ttu-id="e7f91-115">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e7f91-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
