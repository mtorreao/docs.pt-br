---
title: Método ICorProfilerModuleEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
ms.openlocfilehash: 6a967f9a50b3220e2d5e206503330a2bab764c4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701634"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="a3ace-102">Método ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="a3ace-102">ICorProfilerModuleEnum::Skip Method</span></span>

<span data-ttu-id="a3ace-103">Avança o cursor do enumerador de sua posição atual para que o número especificado de elementos seja ignorado.</span><span class="sxs-lookup"><span data-stu-id="a3ace-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ace-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a3ace-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3ace-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a3ace-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="a3ace-106">no O número de elementos a serem ignorados.</span><span class="sxs-lookup"><span data-stu-id="a3ace-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3ace-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="a3ace-107">Return Value</span></span>  

 <span data-ttu-id="a3ace-108">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="a3ace-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a3ace-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3ace-109">HRESULT</span></span>|<span data-ttu-id="a3ace-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="a3ace-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3ace-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3ace-111">S_OK</span></span>|<span data-ttu-id="a3ace-112">`celt` os elementos foram ignorados.</span><span class="sxs-lookup"><span data-stu-id="a3ace-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="a3ace-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a3ace-113">S_FALSE</span></span>|<span data-ttu-id="a3ace-114">Menos de `celt` elementos foram ignorados, o que indica que não há mais elementos.</span><span class="sxs-lookup"><span data-stu-id="a3ace-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3ace-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="a3ace-115">Remarks</span></span>  

 <span data-ttu-id="a3ace-116">A nova posição do cursor deste enumerador é (posição atual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="a3ace-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3ace-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3ace-117">Requirements</span></span>  

 <span data-ttu-id="a3ace-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3ace-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3ace-119">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a3ace-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3ace-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3ace-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3ace-121">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ace-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ace-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3ace-122">See also</span></span>

- [<span data-ttu-id="a3ace-123">Interface ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="a3ace-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="a3ace-124">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="a3ace-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
