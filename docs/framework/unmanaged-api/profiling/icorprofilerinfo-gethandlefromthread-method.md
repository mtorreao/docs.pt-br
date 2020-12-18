---
title: Método ICorProfilerInfo::GetHandleFromThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
ms.openlocfilehash: 94c2c6e01e4188f1fa13c3b6a9f638d4b79a502f
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678187"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="900fe-102">Método ICorProfilerInfo::GetHandleFromThread</span><span class="sxs-lookup"><span data-stu-id="900fe-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>

<span data-ttu-id="900fe-103">Mapeia a ID de um thread para um identificador de thread do Win32.</span><span class="sxs-lookup"><span data-stu-id="900fe-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="900fe-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="900fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="900fe-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="900fe-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="900fe-106">no A ID do thread a ser mapeada.</span><span class="sxs-lookup"><span data-stu-id="900fe-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="900fe-107">fora Um ponteiro para um identificador de Thread Win32.</span><span class="sxs-lookup"><span data-stu-id="900fe-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="900fe-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="900fe-108">Remarks</span></span>  

 <span data-ttu-id="900fe-109">O criador de perfil deve chamar a função do Win32 `DuplicateHandle` na alça antes de usá-la.</span><span class="sxs-lookup"><span data-stu-id="900fe-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  

 <span data-ttu-id="900fe-110">O identificador retornado por esse método pertence ao tempo de execução e o criador de perfil nunca deve fechá-lo.</span><span class="sxs-lookup"><span data-stu-id="900fe-110">The handle returned from this method is owned by the runtime and the profiler should never close it.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="900fe-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="900fe-111">Requirements</span></span>  

 <span data-ttu-id="900fe-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="900fe-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="900fe-113">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="900fe-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="900fe-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="900fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="900fe-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="900fe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="900fe-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="900fe-116">See also</span></span>

- [<span data-ttu-id="900fe-117">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="900fe-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
