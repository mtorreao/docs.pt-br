---
title: Método ICorProfilerThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
ms.openlocfilehash: dc8e85c5a6047ad5dd99520b57789605333d5bf2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721199"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="acb21-102">Método ICorProfilerThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="acb21-102">ICorProfilerThreadEnum::Next Method</span></span>

<span data-ttu-id="acb21-103">Obtém o número especificado de threads contíguos de uma coleção sequencial de threads, começando na posição atual do enumerador na sequência.</span><span class="sxs-lookup"><span data-stu-id="acb21-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb21-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="acb21-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acb21-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="acb21-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="acb21-106">no O número de threads a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="acb21-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="acb21-107">fora Uma matriz de `ThreadID` valores, cada um representando um thread recuperado.</span><span class="sxs-lookup"><span data-stu-id="acb21-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="acb21-108">fora Um ponteiro para o número de threads realmente retornados na `ids` matriz.</span><span class="sxs-lookup"><span data-stu-id="acb21-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acb21-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="acb21-109">Return Value</span></span>  

 <span data-ttu-id="acb21-110">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="acb21-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="acb21-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="acb21-111">HRESULT</span></span>|<span data-ttu-id="acb21-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="acb21-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acb21-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="acb21-113">S_OK</span></span>|<span data-ttu-id="acb21-114">`celt` elementos foram retornados.</span><span class="sxs-lookup"><span data-stu-id="acb21-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="acb21-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="acb21-115">S_FALSE</span></span>|<span data-ttu-id="acb21-116">Menos de `celt` elementos foram retornados, o que indica que a enumeração foi concluída.</span><span class="sxs-lookup"><span data-stu-id="acb21-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acb21-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acb21-117">Requirements</span></span>  

 <span data-ttu-id="acb21-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acb21-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acb21-119">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="acb21-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="acb21-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acb21-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acb21-121">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acb21-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb21-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="acb21-122">See also</span></span>

- [<span data-ttu-id="acb21-123">Interface ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="acb21-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="acb21-124">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="acb21-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
