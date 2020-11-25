---
title: Método ICorProfilerCallback::ExceptionCatcherLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
ms.openlocfilehash: c0a24a8f9b7c40d87f9b9b6fe77eba7d6c0ea89f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700022"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="77834-102">Método ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="77834-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>

<span data-ttu-id="77834-103">Notifica o criador de perfil que o controle está sendo passado para fora do `catch` bloco apropriado.</span><span class="sxs-lookup"><span data-stu-id="77834-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77834-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="77834-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="77834-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="77834-105">Remarks</span></span>  

 <span data-ttu-id="77834-106">O criador de perfil não deve bloquear em sua implementação desse método porque a pilha pode não estar em um estado que permita a coleta de lixo e, portanto, a coleta de lixo preemptiva não pode ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="77834-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="77834-107">Se o criador de perfil for bloqueado aqui e a coleta de lixo for tentada, o tempo de execução será bloqueado até que esse retorno de chamada seja retornado.</span><span class="sxs-lookup"><span data-stu-id="77834-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="77834-108">A implementação do criador de perfil desse método não deve chamar o código gerenciado ou, de qualquer forma, causar uma alocação de memória gerenciada.</span><span class="sxs-lookup"><span data-stu-id="77834-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77834-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77834-109">Requirements</span></span>  

 <span data-ttu-id="77834-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77834-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77834-111">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="77834-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="77834-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77834-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77834-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77834-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77834-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="77834-114">See also</span></span>

- [<span data-ttu-id="77834-115">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="77834-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="77834-116">Método ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="77834-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
