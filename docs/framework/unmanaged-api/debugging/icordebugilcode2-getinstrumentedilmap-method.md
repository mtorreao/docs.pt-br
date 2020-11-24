---
title: ICorDebugILCode2::Método GetInstrumentedILMap
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 097502f4321531922d6c4385e2eccbf32f66f026
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688348"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="d7307-102">ICorDebugILCode2::Método GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="d7307-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>

<span data-ttu-id="d7307-103">[Com suporte no .NET Framework 4.5.2 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="d7307-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d7307-104">Retorna um mapa dos deslocamentos da linguagem intermediária (IL) instrumentados pelo criador de perfis para os deslocamentos da IL do método original para esta instância.</span><span class="sxs-lookup"><span data-stu-id="d7307-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7307-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d7307-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7307-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d7307-106">Parameters</span></span>  

 <span data-ttu-id="d7307-107">cMap</span><span class="sxs-lookup"><span data-stu-id="d7307-107">cMap</span></span>  
 <span data-ttu-id="d7307-108">[in] A capacidade de armazenamento da matriz de `map`.</span><span class="sxs-lookup"><span data-stu-id="d7307-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="d7307-109">Consulte a seção Comentários para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d7307-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="d7307-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="d7307-110">pcMap</span></span>  
 <span data-ttu-id="d7307-111">[out] O número dos valores COR_IL_MAP gravados na matriz de mapa.</span><span class="sxs-lookup"><span data-stu-id="d7307-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="d7307-112">map</span><span class="sxs-lookup"><span data-stu-id="d7307-112">map</span></span>  
 <span data-ttu-id="d7307-113">[out] Uma matriz de valores do COR_IL_MAP que fornece informações sobre mapeamentos da IL instrumentada pelo criador de perfis para a IL do método original.</span><span class="sxs-lookup"><span data-stu-id="d7307-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7307-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="d7307-114">Remarks</span></span>  

 <span data-ttu-id="d7307-115">Se o criador de perfil definir o mapeamento chamando o método [ICorProfilerInfo:: SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , o depurador poderá chamar esse método para recuperar o mapeamento e usar o mapeamento internamente ao calcular deslocamentos de Il para rastreamentos de pilha e tempos de vida variáveis.</span><span class="sxs-lookup"><span data-stu-id="d7307-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="d7307-116">Se `cMap` for 0 e `pcMap` for não **nulo**, `pcMap` será definido como o número de valores de COR_IL_MAP disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d7307-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="d7307-117">Se `cMap` for não zero, representará a capacidade de armazenamento da matriz do `map`.</span><span class="sxs-lookup"><span data-stu-id="d7307-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="d7307-118">Quando o método retorna, `map` contém um máximo de `cMap` itens e `pcMap` é definido como o número de COR_IL_MAP valores gravados na `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="d7307-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="d7307-119">Se a IL não tiver sido instrumentada ou o mapeamento não tiver sido fornecido por um criador de perfil, esse método retorna `S_OK` e define `pcMap` para 0.</span><span class="sxs-lookup"><span data-stu-id="d7307-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7307-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7307-120">Requirements</span></span>  

 <span data-ttu-id="d7307-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7307-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7307-122">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7307-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7307-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7307-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7307-124">**.NET Framework versões:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7307-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7307-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="d7307-125">See also</span></span>

- [<span data-ttu-id="d7307-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="d7307-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="d7307-127">Interface ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="d7307-127">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="d7307-128">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="d7307-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
