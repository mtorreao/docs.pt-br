---
title: Interface ICorProfilerCallback5
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: 8e94aebc489fff1c81593e54b17c471e7228d810
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689284"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="bae18-102">Interface ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="bae18-102">ICorProfilerCallback5 Interface</span></span>

<span data-ttu-id="bae18-103">Complementa as informações para ajudar um criador de perfil a identificar o fechamento completo de objetos dinâmicos, quando usado com o método [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) ou [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) junto com os métodos [ICorProfilerCallback:: objectreferenciations](icorprofilercallback-objectreferences-method.md) e [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bae18-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="bae18-104">O `ICorProfilerCallback5` deve ser implementado por um criador de perfil de memória gerenciada para assinar as notificações relacionadas aos identificadores dependentes.</span><span class="sxs-lookup"><span data-stu-id="bae18-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bae18-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="bae18-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bae18-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="bae18-106">Methods</span></span>  
  
|<span data-ttu-id="bae18-107">Método</span><span class="sxs-lookup"><span data-stu-id="bae18-107">Method</span></span>|<span data-ttu-id="bae18-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="bae18-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bae18-109">Método ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="bae18-109">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="bae18-110">Identifica o fechamento transitivo de objetos referenciados por estas raízes por meio de referências diretas do campo de membro e de dependências `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="bae18-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bae18-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bae18-111">Requirements</span></span>  

 <span data-ttu-id="bae18-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bae18-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bae18-113">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="bae18-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bae18-114">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bae18-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae18-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="bae18-115">See also</span></span>

- [<span data-ttu-id="bae18-116">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="bae18-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="bae18-117">Interface ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="bae18-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
