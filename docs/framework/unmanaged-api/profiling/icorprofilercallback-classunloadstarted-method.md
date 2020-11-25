---
title: Método ICorProfilerCallback::ClassUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 1c154eee85811796321aea2647db1c8996997576
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700217"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="31181-102">Método ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="31181-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>

<span data-ttu-id="31181-103">Notifica o criador de perfil de que uma classe está sendo descarregada.</span><span class="sxs-lookup"><span data-stu-id="31181-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31181-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="31181-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31181-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="31181-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="31181-106">\[in] identifica a classe que está sendo descarregada.</span><span class="sxs-lookup"><span data-stu-id="31181-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="31181-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="31181-107">Remarks</span></span>  

 <span data-ttu-id="31181-108">O valor de `classId` não é válido para uma solicitação de informações após o `ClassUnloadStarted` retorno do método — essa é a última chance do criador de perfil obter informações sobre essa classe.</span><span class="sxs-lookup"><span data-stu-id="31181-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31181-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31181-109">Requirements</span></span>  

 <span data-ttu-id="31181-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31181-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31181-111">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="31181-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31181-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31181-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31181-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31181-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31181-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="31181-114">See also</span></span>

- [<span data-ttu-id="31181-115">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="31181-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="31181-116">Método ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="31181-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
