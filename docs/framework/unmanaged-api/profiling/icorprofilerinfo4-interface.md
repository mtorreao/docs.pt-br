---
title: Interface ICorProfilerInfo4
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: c3e623b0b5f8b49e043fe3a1aa8311558e573573
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682829"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="07403-102">Interface ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="07403-102">ICorProfilerInfo4 Interface</span></span>

<span data-ttu-id="07403-103">Fornece métodos que os profileres de código usam para se comunicar com o Common Language Runtime (CLR) para controlar o monitoramento de eventos e informações de solicitação.</span><span class="sxs-lookup"><span data-stu-id="07403-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="07403-104">.</span><span class="sxs-lookup"><span data-stu-id="07403-104">.</span></span> <span data-ttu-id="07403-105">A `ICorProfilerInfo4` interface é uma extensão das outras `ICorProfilerInfo` interfaces.</span><span class="sxs-lookup"><span data-stu-id="07403-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="07403-106">Ele fornece novos métodos para dar suporte à recompilação JIT (just-in-time), adicionada ao .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="07403-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07403-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="07403-107">Methods</span></span>  
  
|<span data-ttu-id="07403-108">Método</span><span class="sxs-lookup"><span data-stu-id="07403-108">Method</span></span>|<span data-ttu-id="07403-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="07403-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07403-110">Método EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="07403-110">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="07403-111">Retorna um enumerador para todas as funções que foram previamente compiladas e recompiladas por JIT.</span><span class="sxs-lookup"><span data-stu-id="07403-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="07403-112">Método EnumThreads</span><span class="sxs-lookup"><span data-stu-id="07403-112">EnumThreads Method</span></span>](icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="07403-113">Obtém um enumerador que fornece métodos para iterar sequencialmente através da coleção de todos os threads gerenciados no processo de perfil.</span><span class="sxs-lookup"><span data-stu-id="07403-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="07403-114">Método GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="07403-114">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="07403-115">Obtém as extensões do código nativo associado à versão recompilada do JIT da função especificada.</span><span class="sxs-lookup"><span data-stu-id="07403-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="07403-116">Método GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="07403-116">GetFunctionFromIP2 Method</span></span>](icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="07403-117">Mapeia um ponteiro de instrução de código gerenciado para a versão recompilada do JIT de uma função especificada.</span><span class="sxs-lookup"><span data-stu-id="07403-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="07403-118">Método GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="07403-118">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="07403-119">Obtém um mapa de deslocamentos de MSIL (Microsoft Intermediate Language) para deslocamentos nativos do código contido na versão recompilada do JIT da função especificada.</span><span class="sxs-lookup"><span data-stu-id="07403-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="07403-120">Método GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="07403-120">GetObjectSize2 Method</span></span>](icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="07403-121">Retorna o tamanho de um objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="07403-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="07403-122">Método GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="07403-122">GetReJITIDs Method</span></span>](icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="07403-123">Retorna uma matriz de IDs que identifica todas as versões recompiladas por JIT da função especificada que ainda estão alocadas.</span><span class="sxs-lookup"><span data-stu-id="07403-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="07403-124">Método InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="07403-124">InitializeCurrentThread Method</span></span>](icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="07403-125">Inicializa o thread atual antes das chamadas de API do criador de perfil subsequentes no mesmo thread, para que o deadlock possa ser evitado.</span><span class="sxs-lookup"><span data-stu-id="07403-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="07403-126">Método RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="07403-126">RequestReJIT Method</span></span>](icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="07403-127">Solicita uma recompilação JIT de todas as instâncias das funções especificadas.</span><span class="sxs-lookup"><span data-stu-id="07403-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="07403-128">Método RequestRevert</span><span class="sxs-lookup"><span data-stu-id="07403-128">RequestRevert Method</span></span>](icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="07403-129">Reverte todas as instâncias das funções especificadas para suas versões originais.</span><span class="sxs-lookup"><span data-stu-id="07403-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07403-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="07403-130">Remarks</span></span>  

 <span data-ttu-id="07403-131">O CLR implementa os métodos da `ICorProfilerInfo4` interface usando o modelo de thread livre.</span><span class="sxs-lookup"><span data-stu-id="07403-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="07403-132">Cada método retorna um HRESULT para indicar êxito ou falha.</span><span class="sxs-lookup"><span data-stu-id="07403-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="07403-133">Para obter uma lista de possíveis códigos de retorno, consulte o arquivo CorError. h.</span><span class="sxs-lookup"><span data-stu-id="07403-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07403-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07403-134">Requirements</span></span>  

 <span data-ttu-id="07403-135">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07403-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07403-136">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="07403-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07403-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07403-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07403-138">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07403-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07403-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="07403-139">See also</span></span>

- [<span data-ttu-id="07403-140">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="07403-140">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="07403-141">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="07403-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
