---
title: Interface ICorProfilerFunctionControl
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 733a8f0bc7e8c19823827297a50f9c6906614ca7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698371"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="e5c7e-102">Interface ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="e5c7e-102">ICorProfilerFunctionControl Interface</span></span>

<span data-ttu-id="e5c7e-103">Fornece métodos que permitem a um criador de perfis de código se comunicar com o Common Language runtime (CLR) para controlar como o compilador JIT deve gerar código ao recompilar um método específico.</span><span class="sxs-lookup"><span data-stu-id="e5c7e-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5c7e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e5c7e-104">Methods</span></span>  
  
|<span data-ttu-id="e5c7e-105">Método</span><span class="sxs-lookup"><span data-stu-id="e5c7e-105">Method</span></span>|<span data-ttu-id="e5c7e-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e5c7e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5c7e-107">Método SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="e5c7e-107">SetCodegenFlags Method</span></span>](icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="e5c7e-108">Define um ou mais sinalizadores da enumeração de [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) para controlar a geração de código para uma função recompilada JIT (just-in-time).</span><span class="sxs-lookup"><span data-stu-id="e5c7e-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="e5c7e-109">Método SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="e5c7e-109">SetILFunctionBody Method</span></span>](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="e5c7e-110">Substitui o corpo CIL (Common Intermediate Language) do método.</span><span class="sxs-lookup"><span data-stu-id="e5c7e-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="e5c7e-111">Método SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="e5c7e-111">SetILInstrumentedCodeMap Method</span></span>](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="e5c7e-112">Define um mapa de códigos para a função especificada usando as entradas de mapa Common Intermediate Language (CIL) especificadas.</span><span class="sxs-lookup"><span data-stu-id="e5c7e-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5c7e-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="e5c7e-113">Remarks</span></span>  

 <span data-ttu-id="e5c7e-114">A interface de `ICorProfilerFunctionControl` fornece métodos para controlar a geração de código para uma única função recompilada.</span><span class="sxs-lookup"><span data-stu-id="e5c7e-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="e5c7e-115">O criador de perfil Obtém uma instância dessa interface por meio do retorno de chamada [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e5c7e-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="e5c7e-116">Cada instância do `ICorProfilerFunctionControl` controla todas as instâncias de uma função.</span><span class="sxs-lookup"><span data-stu-id="e5c7e-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c7e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5c7e-117">Requirements</span></span>  

 <span data-ttu-id="e5c7e-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5c7e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5c7e-119">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="e5c7e-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5c7e-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5c7e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5c7e-121">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5c7e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c7e-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="e5c7e-122">See also</span></span>

- [<span data-ttu-id="e5c7e-123">Interface ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="e5c7e-123">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="e5c7e-124">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="e5c7e-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e5c7e-125">Método EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="e5c7e-125">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)
