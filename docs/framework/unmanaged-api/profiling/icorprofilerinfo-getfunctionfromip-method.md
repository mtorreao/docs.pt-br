---
title: Método ICorProfilerInfo::GetFunctionFromIP
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: 4a7e21ae60253c741b57674212e0ecabdd844d2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722543"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="38d53-102">Método ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="38d53-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="38d53-103">Mapeia um ponteiro de instrução de código gerenciado para um `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="38d53-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d53-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="38d53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38d53-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="38d53-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="38d53-106">\[in] o ponteiro de instrução no código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="38d53-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="38d53-107">\[out] a ID da função retornada.</span><span class="sxs-lookup"><span data-stu-id="38d53-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="38d53-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38d53-108">Requirements</span></span>  

 <span data-ttu-id="38d53-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d53-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d53-110">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="38d53-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38d53-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38d53-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38d53-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d53-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d53-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="38d53-113">See also</span></span>

- [<span data-ttu-id="38d53-114">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="38d53-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
