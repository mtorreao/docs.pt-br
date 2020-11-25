---
title: Método ICorProfilerInfo::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: 376b9fc637993f00722c48db7f51650e0a22d931
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720913"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="bc645-102">Método ICorProfilerInfo::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="bc645-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>

<span data-ttu-id="bc645-103">Substitui o corpo da função especificada no módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="bc645-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc645-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bc645-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc645-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bc645-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="bc645-106">no A ID do módulo no qual a função reside.</span><span class="sxs-lookup"><span data-stu-id="bc645-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="bc645-107">no O token da função para a qual substituir o corpo.</span><span class="sxs-lookup"><span data-stu-id="bc645-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="bc645-108">no O novo cabeçalho da função.</span><span class="sxs-lookup"><span data-stu-id="bc645-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc645-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="bc645-109">Remarks</span></span>  

 <span data-ttu-id="bc645-110">O `SetILFunctionBody` método substitui o endereço virtual relativo da função nos metadados para que ele aponte para o novo corpo da função e ajusta todas as estruturas de dados internas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="bc645-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="bc645-111">O `SetILFunctionBody` método pode ser chamado somente nas funções que nunca foram compiladas por um compilador JIT (just-in-time).</span><span class="sxs-lookup"><span data-stu-id="bc645-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="bc645-112">Use o método [ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) para alocar espaço para o novo método a fim de garantir que o buffer seja compatível.</span><span class="sxs-lookup"><span data-stu-id="bc645-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc645-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc645-113">Requirements</span></span>  

 <span data-ttu-id="bc645-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc645-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc645-115">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="bc645-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc645-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc645-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc645-117">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc645-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc645-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="bc645-118">See also</span></span>

- [<span data-ttu-id="bc645-119">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="bc645-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
