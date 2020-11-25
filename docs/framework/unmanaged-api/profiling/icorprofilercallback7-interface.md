---
title: Interface ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: e9c7186b3217c29805327e6c1d6b10f580c3a9e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725450"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="7430f-102">Interface ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="7430f-102">ICorProfilerCallback7 Interface</span></span>

<span data-ttu-id="7430f-103">[Com suporte no .NET Framework 4.6.1 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="7430f-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="7430f-104">Uma subclasse de [ICorProfilerCallback6](icorprofilercallback6-interface.md) que fornece um método de retorno de chamada que o Common Language Runtime usa para notificar o criador de perfil de que o fluxo de símbolos associado a um módulo na memória é atualizado.</span><span class="sxs-lookup"><span data-stu-id="7430f-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7430f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7430f-105">Methods</span></span>  
  
|<span data-ttu-id="7430f-106">Método</span><span class="sxs-lookup"><span data-stu-id="7430f-106">Method</span></span>|<span data-ttu-id="7430f-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7430f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7430f-108">Método ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="7430f-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="7430f-109">Notifica o criador de perfil de que o fluxo de símbolos associado a um módulo na memória é atualizado.</span><span class="sxs-lookup"><span data-stu-id="7430f-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7430f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7430f-110">Requirements</span></span>  

 <span data-ttu-id="7430f-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7430f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7430f-112">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="7430f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7430f-113">**.NET Framework versões:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7430f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7430f-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="7430f-114">See also</span></span>

- [<span data-ttu-id="7430f-115">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="7430f-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
