---
title: Método ICorProfilerCallback::AssemblyLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: fd41463af0acac1bbe1a3d4515350905b6784f79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685312"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="b9ed9-102">Método ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="b9ed9-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>

<span data-ttu-id="b9ed9-103">Notifica o criador de perfil que concluiu o carregamento de um assembly.</span><span class="sxs-lookup"><span data-stu-id="b9ed9-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ed9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b9ed9-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9ed9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b9ed9-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="b9ed9-106">\[in] identifica o assembly que foi carregado.</span><span class="sxs-lookup"><span data-stu-id="b9ed9-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="b9ed9-107">\[in] um HRESULT que indica se o assembly terminou de ser carregado com êxito.</span><span class="sxs-lookup"><span data-stu-id="b9ed9-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9ed9-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="b9ed9-108">Remarks</span></span>  

 <span data-ttu-id="b9ed9-109">O valor de `assemblyId` não é válido para uma solicitação de informações até que o `AssemblyLoadFinished` método seja chamado.</span><span class="sxs-lookup"><span data-stu-id="b9ed9-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="b9ed9-110">Algumas partes do carregamento do assembly podem continuar após o `AssemblyLoadFinished` retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="b9ed9-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="b9ed9-111">Um HRESULT de falha em `hrStatus` indica uma falha.</span><span class="sxs-lookup"><span data-stu-id="b9ed9-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="b9ed9-112">No entanto, um HRESULT de êxito em `hrStatus` indica apenas que a primeira parte do carregamento do assembly foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b9ed9-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ed9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9ed9-113">Requirements</span></span>  

 <span data-ttu-id="b9ed9-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9ed9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ed9-115">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b9ed9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9ed9-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9ed9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9ed9-117">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ed9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ed9-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9ed9-118">See also</span></span>

- [<span data-ttu-id="b9ed9-119">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b9ed9-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
