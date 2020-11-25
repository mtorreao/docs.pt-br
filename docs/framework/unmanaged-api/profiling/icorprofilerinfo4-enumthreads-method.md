---
title: Método ICorProfilerInfo4::EnumThreads
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: df0e66c8563404d7de4f1e11f41483f2f61f519c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721550"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="b7097-102">Método ICorProfilerInfo4::EnumThreads</span><span class="sxs-lookup"><span data-stu-id="b7097-102">ICorProfilerInfo4::EnumThreads Method</span></span>

<span data-ttu-id="b7097-103">Retorna um enumerador que fornece métodos para iterar sequencialmente pela coleção de todos os threads gerenciados no processo de perfil.</span><span class="sxs-lookup"><span data-stu-id="b7097-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7097-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b7097-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7097-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b7097-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="b7097-106">fora Um ponteiro para uma interface [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b7097-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7097-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="b7097-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7097-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7097-108">Requirements</span></span>  

 <span data-ttu-id="b7097-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7097-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7097-110">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b7097-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7097-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7097-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7097-112">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7097-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7097-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="b7097-113">See also</span></span>

- [<span data-ttu-id="b7097-114">Interface ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="b7097-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="b7097-115">Interface ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="b7097-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="b7097-116">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="b7097-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b7097-117">Criação de perfil</span><span class="sxs-lookup"><span data-stu-id="b7097-117">Profiling</span></span>](index.md)
