---
title: Interface ICorDebugEnum
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: b208444de3b427329988f27b9d252b54143b7240
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698787"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="c7687-102">Interface ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="c7687-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="c7687-103">Serve como a interface base abstrata para os enumeradores que são usados por um aplicativo de depuração.</span><span class="sxs-lookup"><span data-stu-id="c7687-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7687-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c7687-104">Methods</span></span>  
  
|<span data-ttu-id="c7687-105">Método</span><span class="sxs-lookup"><span data-stu-id="c7687-105">Method</span></span>|<span data-ttu-id="c7687-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c7687-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7687-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="c7687-107">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="c7687-108">Cria uma cópia deste objeto `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="c7687-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="c7687-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="c7687-109">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="c7687-110">Obtém o número de itens na enumeração.</span><span class="sxs-lookup"><span data-stu-id="c7687-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="c7687-111">Método Reset</span><span class="sxs-lookup"><span data-stu-id="c7687-111">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="c7687-112">Move o cursor para o início da enumeração.</span><span class="sxs-lookup"><span data-stu-id="c7687-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="c7687-113">Método Skip</span><span class="sxs-lookup"><span data-stu-id="c7687-113">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="c7687-114">Move o cursor para a frente na enumeração pelo número especificado de itens.</span><span class="sxs-lookup"><span data-stu-id="c7687-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7687-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="c7687-115">Remarks</span></span>  

 <span data-ttu-id="c7687-116">Os seguintes enumeradores derivam de `ICorDebugEnum` :</span><span class="sxs-lookup"><span data-stu-id="c7687-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="c7687-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="c7687-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="c7687-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c7687-119">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="c7687-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="c7687-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="c7687-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="c7687-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="c7687-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="c7687-124">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="c7687-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="c7687-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="c7687-126">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="c7687-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="c7687-127">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="c7687-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="c7687-128">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="c7687-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="c7687-129">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="c7687-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="c7687-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="c7687-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="c7687-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="c7687-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="c7687-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="c7687-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="c7687-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="c7687-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="c7687-137">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="c7687-138">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="c7687-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7687-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7687-139">Requirements</span></span>  

 <span data-ttu-id="c7687-140">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7687-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7687-141">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7687-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7687-142">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7687-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7687-143">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7687-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7687-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="c7687-144">See also</span></span>

- [<span data-ttu-id="c7687-145">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="c7687-145">Debugging Interfaces</span></span>](debugging-interfaces.md)
