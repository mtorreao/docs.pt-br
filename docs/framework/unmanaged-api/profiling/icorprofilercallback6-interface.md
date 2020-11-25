---
title: Interface ICorProfilerCallback6
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 2176b624a427994b9d2af4b5eba31a64c9288a0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725463"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="cd2df-102">Interface ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="cd2df-102">ICorProfilerCallback6 Interface</span></span>

<span data-ttu-id="cd2df-103">[Com suporte no .NET Framework 4.5.2 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="cd2df-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="cd2df-104">Uma subclasse de [ICorProfilerCallback5](icorprofilercallback5-interface.md) que fornece um método de retorno de chamada que o Common Language Runtime usa para notificar um criador de perfil que um assembly está carregando.</span><span class="sxs-lookup"><span data-stu-id="cd2df-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd2df-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cd2df-105">Methods</span></span>  
  
|<span data-ttu-id="cd2df-106">Método</span><span class="sxs-lookup"><span data-stu-id="cd2df-106">Method</span></span>|<span data-ttu-id="cd2df-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="cd2df-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd2df-108">Método GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="cd2df-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="cd2df-109">Notifica o criador de perfis de que um assembly está em um estágio inicial de carregamento, quando o Common Language Runtime realiza um exame de fechamento da referência do assembly.</span><span class="sxs-lookup"><span data-stu-id="cd2df-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd2df-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="cd2df-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd2df-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd2df-111">Requirements</span></span>  

 <span data-ttu-id="cd2df-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd2df-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd2df-113">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="cd2df-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd2df-114">**.NET Framework versões:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd2df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd2df-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd2df-115">See also</span></span>

- [<span data-ttu-id="cd2df-116">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="cd2df-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
