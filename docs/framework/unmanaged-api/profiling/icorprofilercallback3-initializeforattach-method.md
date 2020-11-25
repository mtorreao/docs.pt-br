---
title: Método ICorProfilerCallback3::InitializeForAttach
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: c85bba9a5d913820b69cbc214275b733a53197ee
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729441"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="5dafd-102">Método ICorProfilerCallback3::InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="5dafd-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>

<span data-ttu-id="5dafd-103">Chamado pelo Common Language Runtime (CLR) para dar ao criador de perfil uma oportunidade de inicializar seu estado após uma operação de anexação.</span><span class="sxs-lookup"><span data-stu-id="5dafd-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dafd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5dafd-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dafd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5dafd-105">Parameters</span></span>  

 `pCorProfilerInfoUnk`  
 <span data-ttu-id="5dafd-106">no Um ponteiro de interface para a `ICorProfilerInfo*` interface.</span><span class="sxs-lookup"><span data-stu-id="5dafd-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="5dafd-107">no Um ponteiro para os dados passados para o método [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) em seu `pvClientData` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5dafd-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="5dafd-108">Se esse parâmetro for NULL, `cbClientData` será 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="5dafd-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="5dafd-109">O CLR libera essa memória quando ela retorna do `InitializeForAttach` .</span><span class="sxs-lookup"><span data-stu-id="5dafd-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="5dafd-110">no O tamanho, em bytes, dos dados que `pvClientData` aponta para.</span><span class="sxs-lookup"><span data-stu-id="5dafd-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dafd-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="5dafd-111">Remarks</span></span>  

 <span data-ttu-id="5dafd-112">O CLR chama `InitializeForAttach` para dar ao criador de perfil uma oportunidade de solicitar retornos de chamada.</span><span class="sxs-lookup"><span data-stu-id="5dafd-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dafd-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dafd-113">Requirements</span></span>  

 <span data-ttu-id="5dafd-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dafd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dafd-115">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="5dafd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5dafd-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5dafd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5dafd-117">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dafd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dafd-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="5dafd-118">See also</span></span>

- [<span data-ttu-id="5dafd-119">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5dafd-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5dafd-120">Interface ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="5dafd-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5dafd-121">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="5dafd-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="5dafd-122">Criação de perfil</span><span class="sxs-lookup"><span data-stu-id="5dafd-122">Profiling</span></span>](index.md)
