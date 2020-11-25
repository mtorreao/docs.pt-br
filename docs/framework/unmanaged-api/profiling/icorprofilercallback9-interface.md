---
title: Interface ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 23b91a2a58c6e76b31b94e0fa3661dfbc8e18e33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712762"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="d5bcc-102">Interface ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="d5bcc-102">ICorProfilerCallback9 Interface</span></span>

<span data-ttu-id="d5bcc-103">[Com suporte no .NET Framework 4.7.2 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="d5bcc-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="d5bcc-104">Uma subclasse de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que fornece um método de retorno de chamada usado pelo Common Language Runtime para notificar o criador de perfil de que um método dinâmico tem sido coletado como lixo e subsequentemente descarregado.</span><span class="sxs-lookup"><span data-stu-id="d5bcc-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5bcc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d5bcc-105">Methods</span></span>  
  
|<span data-ttu-id="d5bcc-106">Método</span><span class="sxs-lookup"><span data-stu-id="d5bcc-106">Method</span></span>|<span data-ttu-id="d5bcc-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d5bcc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5bcc-108">Método DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="d5bcc-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="d5bcc-109">Notifica o criador de perfil de que um método dinâmico foi coletado como lixo e subsequentemente descarregado.</span><span class="sxs-lookup"><span data-stu-id="d5bcc-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5bcc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5bcc-110">Requirements</span></span>  

 <span data-ttu-id="d5bcc-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5bcc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5bcc-112">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="d5bcc-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="d5bcc-113">**.NET Framework versões:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d5bcc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d5bcc-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="d5bcc-114">See also</span></span>

- [<span data-ttu-id="d5bcc-115">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="d5bcc-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d5bcc-116">Interface ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="d5bcc-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="d5bcc-117">Método ICorProfilerCallback8. DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d5bcc-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="d5bcc-118">Método ICorProfilerCallback8. DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="d5bcc-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
