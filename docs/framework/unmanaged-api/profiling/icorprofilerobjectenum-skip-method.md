---
title: Método ICorProfilerObjectEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
ms.openlocfilehash: 83c6af74ebc3eb668317bd64628af17513a2aed6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702349"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="0761b-102">Método ICorProfilerObjectEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="0761b-102">ICorProfilerObjectEnum::Skip Method</span></span>

<span data-ttu-id="0761b-103">Avança o cursor deste enumerador de sua posição atual para que o número especificado de elementos seja ignorado.</span><span class="sxs-lookup"><span data-stu-id="0761b-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0761b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0761b-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0761b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0761b-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="0761b-106">no O número de elementos a serem ignorados.</span><span class="sxs-lookup"><span data-stu-id="0761b-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0761b-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="0761b-107">Remarks</span></span>  

 <span data-ttu-id="0761b-108">A nova posição do cursor deste enumerador é: (posição atual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="0761b-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0761b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0761b-109">Requirements</span></span>  

 <span data-ttu-id="0761b-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0761b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0761b-111">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="0761b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0761b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0761b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0761b-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0761b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0761b-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="0761b-114">See also</span></span>

- [<span data-ttu-id="0761b-115">Interface ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="0761b-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
