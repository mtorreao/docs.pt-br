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
ms.openlocfilehash: 632a9070eab227bc48ce76c51ea08f98060d680d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722525"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="e8468-102">Método ICorProfilerInfo::GetHandleFromThread</span><span class="sxs-lookup"><span data-stu-id="e8468-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>

<span data-ttu-id="e8468-103">Mapeia a ID de um thread para um identificador de thread do Win32.</span><span class="sxs-lookup"><span data-stu-id="e8468-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8468-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e8468-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8468-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e8468-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="e8468-106">no A ID do thread a ser mapeada.</span><span class="sxs-lookup"><span data-stu-id="e8468-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="e8468-107">fora Um ponteiro para um identificador de Thread Win32.</span><span class="sxs-lookup"><span data-stu-id="e8468-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8468-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="e8468-108">Remarks</span></span>  

 <span data-ttu-id="e8468-109">O criador de perfil deve chamar a função do Win32 `DuplicateHandle` na alça antes de usá-la.</span><span class="sxs-lookup"><span data-stu-id="e8468-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8468-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8468-110">Requirements</span></span>  

 <span data-ttu-id="e8468-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8468-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8468-112">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="e8468-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8468-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8468-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8468-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8468-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8468-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="e8468-115">See also</span></span>

- [<span data-ttu-id="e8468-116">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e8468-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
