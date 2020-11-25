---
title: Método ICorProfilerCallback::RootReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: 2d084ce0a785ba37c5b7dc937ed116cee74b7594
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720653"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="89e7d-102">Método ICorProfilerCallback::RootReferences</span><span class="sxs-lookup"><span data-stu-id="89e7d-102">ICorProfilerCallback::RootReferences Method</span></span>

<span data-ttu-id="89e7d-103">Notifica o criador de perfil com informações sobre referências raiz após a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="89e7d-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e7d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="89e7d-104">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="89e7d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="89e7d-105">Parameters</span></span>  

 `cRootRefs`  
 <span data-ttu-id="89e7d-106">no O número de referências na `rootRefIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="89e7d-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="89e7d-107">no Uma matriz de IDs de objeto que fazem referência a um objeto estático ou a um objeto na pilha.</span><span class="sxs-lookup"><span data-stu-id="89e7d-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89e7d-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="89e7d-108">Remarks</span></span>  

 <span data-ttu-id="89e7d-109">Ambos `RootReferences` e [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) são chamados para notificar o criador de perfil.</span><span class="sxs-lookup"><span data-stu-id="89e7d-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="89e7d-110">Os profileres normalmente implementarão um ou outro, mas não ambos, porque as informações transmitidas `RootReferences2` são um superconjunto do passado `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="89e7d-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="89e7d-111">É possível que a `rootRefIds` matriz contenha um objeto nulo.</span><span class="sxs-lookup"><span data-stu-id="89e7d-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="89e7d-112">Por exemplo, todas as referências de objeto declaradas na pilha são tratadas como raízes pelo coletor de lixo e sempre serão relatadas.</span><span class="sxs-lookup"><span data-stu-id="89e7d-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="89e7d-113">As IDs de objeto retornadas por `RootReferences` não são válidas durante o próprio retorno de chamada, pois a coleta de lixo pode estar no meio da movimentação de objetos de endereços antigos para novos endereços.</span><span class="sxs-lookup"><span data-stu-id="89e7d-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="89e7d-114">Portanto, os profileres não devem tentar inspecionar objetos durante uma `RootReferences` chamada.</span><span class="sxs-lookup"><span data-stu-id="89e7d-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="89e7d-115">Quando [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) é chamado, todos os objetos foram movidos para seus novos locais e podem ser inspecionados com segurança.</span><span class="sxs-lookup"><span data-stu-id="89e7d-115">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e7d-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89e7d-116">Requirements</span></span>  

 <span data-ttu-id="89e7d-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89e7d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e7d-118">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="89e7d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89e7d-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89e7d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89e7d-120">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e7d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e7d-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="89e7d-121">See also</span></span>

- [<span data-ttu-id="89e7d-122">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="89e7d-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
