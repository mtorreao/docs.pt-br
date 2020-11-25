---
title: Método ICorProfilerCallback::ObjectReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 9485e3ca657ab108d2bcc9d00b1c475f8ee3c086
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703948"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="2f2e6-102">Método ICorProfilerCallback::ObjectReferences</span><span class="sxs-lookup"><span data-stu-id="2f2e6-102">ICorProfilerCallback::ObjectReferences Method</span></span>

<span data-ttu-id="2f2e6-103">Notifica o criador de perfil sobre objetos na memória que estão sendo referenciados pelo objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2e6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2f2e6-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f2e6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2f2e6-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="2f2e6-106">no A ID do objeto que está fazendo referência a objetos.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="2f2e6-107">no A ID da classe da qual o objeto especificado é uma instância do.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="2f2e6-108">no O número de objetos referenciados pelo objeto especificado (ou seja, o número de elementos na `objectRefIds` matriz).</span><span class="sxs-lookup"><span data-stu-id="2f2e6-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="2f2e6-109">no Uma matriz de IDs de objetos que estão sendo referenciados pelo `objectId` .</span><span class="sxs-lookup"><span data-stu-id="2f2e6-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f2e6-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="2f2e6-110">Remarks</span></span>  

 <span data-ttu-id="2f2e6-111">O `ObjectReferences` método é chamado para cada objeto restante no heap após a conclusão de uma coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="2f2e6-112">Se o criador de perfil retornar um erro desse retorno de chamada, os serviços de criação de perfil descontinuarão invocando esse retorno de chamada até a próxima coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="2f2e6-113">O `ObjectReferences` retorno de chamada pode ser usado em conjunto com o retorno de chamada [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) para criar um grafo de referência de objeto completo para o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="2f2e6-114">O Common Language Runtime (CLR) garante que cada referência de objeto seja relatada apenas uma vez pelo `ObjectReferences` método.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="2f2e6-115">As IDs de objeto retornadas por `ObjectReferences` não são válidas durante o próprio retorno de chamada, pois a coleta de lixo pode estar no meio da movimentação de objetos.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="2f2e6-116">Portanto, os profileres não devem tentar inspecionar objetos durante uma `ObjectReferences` chamada.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="2f2e6-117">Quando [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) é chamado, a coleta de lixo é concluída e a inspeção pode ser feita com segurança.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-117">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="2f2e6-118">Um NULL `ClassId` indica que `objectId` tem um tipo que está descarregando.</span><span class="sxs-lookup"><span data-stu-id="2f2e6-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f2e6-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f2e6-119">Requirements</span></span>  

 <span data-ttu-id="2f2e6-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f2e6-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f2e6-121">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="2f2e6-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f2e6-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f2e6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f2e6-123">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f2e6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2e6-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="2f2e6-124">See also</span></span>

- [<span data-ttu-id="2f2e6-125">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2f2e6-125">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
