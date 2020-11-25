---
title: Método ICorProfilerCallback::ModuleUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: 12d5f7e073337af6034b8f313a2e0161620a65ea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720946"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="9f78f-102">Método ICorProfilerCallback::ModuleUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="9f78f-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>

<span data-ttu-id="9f78f-103">Notifica o criador de perfil de que um módulo está sendo descarregado.</span><span class="sxs-lookup"><span data-stu-id="9f78f-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f78f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f78f-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a><span data-ttu-id="9f78f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9f78f-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="9f78f-106">no A ID do módulo que está sendo descarregado.</span><span class="sxs-lookup"><span data-stu-id="9f78f-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f78f-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="9f78f-107">Remarks</span></span>  

 <span data-ttu-id="9f78f-108">O valor de `moduleId` não é válido para uma solicitação de informações após o `ModuleUnloadStarted` retorno do método — essa é a última chance do criador de perfil obter informações sobre esse módulo.</span><span class="sxs-lookup"><span data-stu-id="9f78f-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f78f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f78f-109">Requirements</span></span>  

 <span data-ttu-id="9f78f-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f78f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f78f-111">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="9f78f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9f78f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f78f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f78f-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f78f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f78f-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f78f-114">See also</span></span>

- [<span data-ttu-id="9f78f-115">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9f78f-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9f78f-116">Método ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="9f78f-116">ModuleUnloadFinished Method</span></span>](icorprofilercallback-moduleunloadfinished-method.md)
