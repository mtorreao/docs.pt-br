---
title: Método ICorProfilerCallback::ExceptionUnwindFunctionEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
ms.openlocfilehash: d3a09a6caf3febd04296fce518ade42e8676a4b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731001"
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="4b9c1-102">Método ICorProfilerCallback::ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="4b9c1-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>

<span data-ttu-id="4b9c1-103">Notifica o criador de perfil de que a fase de desenrolamento da manipulação de exceções começou a desenrolar uma função.</span><span class="sxs-lookup"><span data-stu-id="4b9c1-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b9c1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4b9c1-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b9c1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4b9c1-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="4b9c1-106">\[in] a ID da função que está sendo desbobinada.</span><span class="sxs-lookup"><span data-stu-id="4b9c1-106">\[in] The ID of the function that is being unwound.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b9c1-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="4b9c1-107">Remarks</span></span>  

 <span data-ttu-id="4b9c1-108">O criador de perfil não deve bloquear em sua implementação desse método porque a pilha pode não estar em um estado que permita a coleta de lixo e, portanto, a coleta de lixo preemptiva não pode ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="4b9c1-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="4b9c1-109">Se o criador de perfil for bloqueado aqui e a coleta de lixo for tentada, o tempo de execução será bloqueado até que esse retorno de chamada seja retornado.</span><span class="sxs-lookup"><span data-stu-id="4b9c1-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="4b9c1-110">A implementação do criador de perfil desse método não deve chamar o código gerenciado ou, de qualquer forma, causar uma alocação de memória gerenciada.</span><span class="sxs-lookup"><span data-stu-id="4b9c1-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b9c1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b9c1-111">Requirements</span></span>  

 <span data-ttu-id="4b9c1-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b9c1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b9c1-113">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="4b9c1-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b9c1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b9c1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b9c1-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b9c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9c1-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="4b9c1-116">See also</span></span>

- [<span data-ttu-id="4b9c1-117">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4b9c1-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4b9c1-118">Método ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="4b9c1-118">ExceptionUnwindFunctionLeave Method</span></span>](icorprofilercallback-exceptionunwindfunctionleave-method.md)
