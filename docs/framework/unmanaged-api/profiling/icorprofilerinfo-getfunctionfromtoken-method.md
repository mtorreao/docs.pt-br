---
title: Método ICorProfilerInfo::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 9c7f01d2e462ad1cb0532be6f369c3118a4deb6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722486"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="6e6cf-102">Método ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="6e6cf-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>

<span data-ttu-id="6e6cf-103">Obtém a ID de uma função.</span><span class="sxs-lookup"><span data-stu-id="6e6cf-103">Gets the ID of a function.</span></span> <span data-ttu-id="6e6cf-104">Esse método é obsoleto no .NET Framework versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="6e6cf-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="6e6cf-105">Em vez disso, use o método [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6e6cf-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e6cf-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e6cf-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e6cf-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e6cf-107">Remarks</span></span>  

 <span data-ttu-id="6e6cf-108">O `GetFunctionFromToken` método não funcionará para funções genéricas ou funções em tipos genéricos; agora é obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6e6cf-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="6e6cf-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` para todas as funções.</span><span class="sxs-lookup"><span data-stu-id="6e6cf-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e6cf-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e6cf-110">Requirements</span></span>  

 <span data-ttu-id="6e6cf-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e6cf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e6cf-112">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="6e6cf-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6e6cf-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e6cf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e6cf-114">**Versões do .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="6e6cf-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6cf-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="6e6cf-115">See also</span></span>

- [<span data-ttu-id="6e6cf-116">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="6e6cf-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
