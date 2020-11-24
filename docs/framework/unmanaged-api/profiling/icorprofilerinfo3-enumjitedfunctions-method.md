---
title: Método ICorProfilerInfo3::EnumJITedFunctions
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
ms.openlocfilehash: 6227baaead518eae2de5913369b72de1072ac052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681490"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="1263d-102">Método ICorProfilerInfo3::EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="1263d-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>

<span data-ttu-id="1263d-103">Retorna um enumerador para todas as funções que foram compiladas por JIT anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1263d-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1263d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1263d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1263d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1263d-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="1263d-106">fora Um ponteiro para o enumerador [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1263d-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1263d-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="1263d-107">Remarks</span></span>  

 <span data-ttu-id="1263d-108">Esse método pode se sobrepor a `JITCompilation` retornos de chamada como o método [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1263d-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="1263d-109">O enumerador retornado por esse método não inclui funções que são carregadas de imagens nativas geradas com Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="1263d-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1263d-110">A enumeração retornada inclui apenas "0" para o valor do `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="1263d-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="1263d-111">Se você precisar `COR_PRF_FUNCTION::reJitId` de valores válidos, use o método [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1263d-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1263d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1263d-112">Requirements</span></span>  

 <span data-ttu-id="1263d-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1263d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1263d-114">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="1263d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1263d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1263d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1263d-116">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1263d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1263d-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="1263d-117">See also</span></span>

- [<span data-ttu-id="1263d-118">Interface ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="1263d-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="1263d-119">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="1263d-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1263d-120">Criação de perfil</span><span class="sxs-lookup"><span data-stu-id="1263d-120">Profiling</span></span>](index.md)
