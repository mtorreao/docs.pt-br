---
title: Método ICorProfilerInfo::GetInprocInspectionIThisThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
ms.openlocfilehash: 8daa84e3abbbc64c9a48d8957b4ad9c6756d0d8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682075"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="b18ec-102">Método ICorProfilerInfo::GetInprocInspectionIThisThread</span><span class="sxs-lookup"><span data-stu-id="b18ec-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>

<span data-ttu-id="b18ec-103">Obtém um objeto que pode ser consultado para a interface ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="b18ec-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="b18ec-104">Esse método é obsoleto no .NET Framework versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="b18ec-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b18ec-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b18ec-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b18ec-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b18ec-106">Parameters</span></span>  

 `ppicd`  
 <span data-ttu-id="b18ec-107">objeto de [saída](/cpp/atl/iunknown) que pode ser consultado para a `ICorDebugThread` interface.</span><span class="sxs-lookup"><span data-stu-id="b18ec-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b18ec-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="b18ec-108">Remarks</span></span>  

 <span data-ttu-id="b18ec-109">Os serviços de depuração Common Language Runtime (CLR) com suporte para a depuração em processo limitada na versão .NET Framework 1,0.</span><span class="sxs-lookup"><span data-stu-id="b18ec-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="b18ec-110">A depuração em processo habilitou um criador de perfil para usar as partes de inspeção da API de depuração.</span><span class="sxs-lookup"><span data-stu-id="b18ec-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b18ec-111">Como resultado dos comentários dos clientes, a depuração em processo foi removida da .NET Framework na versão 2,0 e substituída por um conjunto de funcionalidades que está mais alinhado com a API de criação de perfil.</span><span class="sxs-lookup"><span data-stu-id="b18ec-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b18ec-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b18ec-112">Requirements</span></span>  

 <span data-ttu-id="b18ec-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b18ec-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b18ec-114">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b18ec-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b18ec-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b18ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b18ec-116">**Versão do .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="b18ec-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18ec-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="b18ec-117">See also</span></span>

- [<span data-ttu-id="b18ec-118">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b18ec-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
