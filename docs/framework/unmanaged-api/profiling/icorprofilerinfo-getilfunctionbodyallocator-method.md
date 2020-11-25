---
title: Método ICorProfilerInfo::GetILFunctionBodyAllocator
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: b18de87cf89985e0f7ec11edf58b43d67720251c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718014"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="79884-102">Método ICorProfilerInfo::GetILFunctionBodyAllocator</span><span class="sxs-lookup"><span data-stu-id="79884-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>

<span data-ttu-id="79884-103">Obtém uma interface que fornece um método para alocar memória a ser usada para alternar o corpo de um método no código MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="79884-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79884-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="79884-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79884-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="79884-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="79884-106">no A ID do módulo no qual o método reside.</span><span class="sxs-lookup"><span data-stu-id="79884-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="79884-107">fora Um ponteiro para uma interface [IMethodMalloc](imethodmalloc-interface.md) que fornece um método para alocar a memória.</span><span class="sxs-lookup"><span data-stu-id="79884-107">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79884-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="79884-108">Remarks</span></span>  

 <span data-ttu-id="79884-109">Um corpo de método no código MSIL deve estar localizado como um endereço virtual relativo (RVA), relativo ao módulo carregado, o que significa que ele segue o módulo dentro de 4 GB.</span><span class="sxs-lookup"><span data-stu-id="79884-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="79884-110">Para tornar mais fácil para uma ferramenta alternar o corpo de um método, o `GetILFunctionBodyAllocator` método garante que a memória seja alocada dentro desse intervalo.</span><span class="sxs-lookup"><span data-stu-id="79884-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79884-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79884-111">Requirements</span></span>  

 <span data-ttu-id="79884-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79884-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79884-113">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="79884-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79884-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79884-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79884-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79884-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79884-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="79884-116">See also</span></span>

- [<span data-ttu-id="79884-117">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="79884-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
