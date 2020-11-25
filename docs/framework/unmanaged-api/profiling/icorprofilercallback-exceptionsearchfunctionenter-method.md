---
title: Método ICorProfilerCallback::ExceptionSearchFunctionEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
ms.openlocfilehash: 9c39d984db62326b31a4760a817ee82def6dd78f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699814"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="1bc90-102">Método ICorProfilerCallback::ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="1bc90-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>

<span data-ttu-id="1bc90-103">Notifica o criador de perfil de que a fase de pesquisa do tratamento de exceções começou a pesquisar uma função para localizar um manipulador para a exceção atual.</span><span class="sxs-lookup"><span data-stu-id="1bc90-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc90-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1bc90-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bc90-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1bc90-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="1bc90-106">\[in] a ID da função que foi inserida.</span><span class="sxs-lookup"><span data-stu-id="1bc90-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1bc90-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bc90-107">Requirements</span></span>  

 <span data-ttu-id="1bc90-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bc90-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bc90-109">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="1bc90-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1bc90-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bc90-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bc90-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bc90-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc90-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="1bc90-112">See also</span></span>

- [<span data-ttu-id="1bc90-113">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1bc90-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1bc90-114">Método ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="1bc90-114">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
