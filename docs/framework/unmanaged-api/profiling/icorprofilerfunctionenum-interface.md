---
title: Interface ICorProfilerFunctionEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
ms.openlocfilehash: 84c3b504dff8a04172dde903c1681c9f3fb2fcd2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669220"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="9b0f8-102">Interface ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="9b0f8-102">ICorProfilerFunctionEnum Interface</span></span>

<span data-ttu-id="9b0f8-103">Fornece métodos para iterar em sequência por meio de uma coleção de funções no Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b0f8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9b0f8-104">Methods</span></span>  
  
|<span data-ttu-id="9b0f8-105">Método</span><span class="sxs-lookup"><span data-stu-id="9b0f8-105">Method</span></span>|<span data-ttu-id="9b0f8-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9b0f8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b0f8-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="9b0f8-107">Clone Method</span></span>](icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="9b0f8-108">Obtém um ponteiro de interface para uma cópia desta `ICorProfilerFunctionEnum` interface.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="9b0f8-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="9b0f8-109">GetCount Method</span></span>](icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="9b0f8-110">Obtém o número de funções que foram carregadas pelo aplicativo ou carregadas de modo forçado pelo criador de perfil.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="9b0f8-111">Método Next</span><span class="sxs-lookup"><span data-stu-id="9b0f8-111">Next Method</span></span>](icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="9b0f8-112">Obtém o número especificado de funções contíguas de uma coleção sequencial de funções, começando na posição atual do enumerador na sequência.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="9b0f8-113">Método Reset</span><span class="sxs-lookup"><span data-stu-id="9b0f8-113">Reset Method</span></span>](icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="9b0f8-114">Move o cursor do enumerador para a posição inicial da sequência.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="9b0f8-115">Método Skip</span><span class="sxs-lookup"><span data-stu-id="9b0f8-115">Skip Method</span></span>](icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="9b0f8-116">Avança o cursor do enumerador de sua posição atual para que o número especificado de elementos seja ignorado.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b0f8-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="9b0f8-117">Remarks</span></span>  

 <span data-ttu-id="9b0f8-118">A `ICorProfilerFunctionEnum` interface é um enumerador.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="9b0f8-119">Ele permite que o destinatário de uma matriz Extraia elementos do remetente a uma taxa apropriada para o destinatário.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="9b0f8-120">Em outras palavras, o receptor é capaz de controlar explicitamente o fluxo de elementos de matriz, evitando, assim, os problemas associados à passagem de matrizes grandes como parâmetros de método.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="9b0f8-121">`ICorProfilerFunctionEnum` enumera em funções que já foram compiladas por JIT, mas não inclui funções que são carregadas de imagens nativas geradas com Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="9b0f8-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b0f8-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b0f8-122">Requirements</span></span>  

 <span data-ttu-id="9b0f8-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b0f8-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b0f8-124">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="9b0f8-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b0f8-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b0f8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b0f8-126">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b0f8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b0f8-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="9b0f8-127">See also</span></span>

- [<span data-ttu-id="9b0f8-128">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="9b0f8-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="9b0f8-129">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="9b0f8-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9b0f8-130">Método EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="9b0f8-130">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
