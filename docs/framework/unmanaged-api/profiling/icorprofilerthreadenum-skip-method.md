---
title: Método ICorProfilerThreadEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: 12b7b53c408388c21d7508f6591ead5ccf55936b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721173"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="92295-102">Método ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="92295-102">ICorProfilerThreadEnum::Skip Method</span></span>

<span data-ttu-id="92295-103">Avança o cursor do enumerador de sua posição atual para ignorar o número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="92295-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92295-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92295-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92295-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="92295-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="92295-106">no O número de elementos a serem ignorados.</span><span class="sxs-lookup"><span data-stu-id="92295-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92295-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="92295-107">Return Value</span></span>  

 <span data-ttu-id="92295-108">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="92295-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="92295-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92295-109">HRESULT</span></span>|<span data-ttu-id="92295-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="92295-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92295-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="92295-111">S_OK</span></span>|<span data-ttu-id="92295-112">`celt` os elementos foram ignorados.</span><span class="sxs-lookup"><span data-stu-id="92295-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="92295-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="92295-113">S_FALSE</span></span>|<span data-ttu-id="92295-114">Menos de `celt` elementos foram ignorados, o que indica que não há mais elementos.</span><span class="sxs-lookup"><span data-stu-id="92295-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92295-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="92295-115">Remarks</span></span>  

 <span data-ttu-id="92295-116">A nova posição do cursor deste enumerador é (posição atual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="92295-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92295-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92295-117">Requirements</span></span>  

 <span data-ttu-id="92295-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92295-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92295-119">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="92295-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92295-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92295-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92295-121">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92295-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92295-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="92295-122">See also</span></span>

- [<span data-ttu-id="92295-123">Interface ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="92295-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="92295-124">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="92295-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
