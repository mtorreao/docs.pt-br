---
title: Método ICorProfilerCallback::RemotingServerInvocationReturned
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
ms.openlocfilehash: ff1670472b34292cb216a1a8817243ced6a938af
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704819"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="f8bfa-102">Método ICorProfilerCallback::RemotingServerInvocationReturned</span><span class="sxs-lookup"><span data-stu-id="f8bfa-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>

<span data-ttu-id="f8bfa-103">Notifica o criador de perfil de que o processo concluiu a invocação de um método em resposta a uma solicitação de invocação de método remoto.</span><span class="sxs-lookup"><span data-stu-id="f8bfa-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8bfa-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f8bfa-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f8bfa-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8bfa-105">Requirements</span></span>  

 <span data-ttu-id="f8bfa-106">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8bfa-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8bfa-107">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="f8bfa-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8bfa-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8bfa-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8bfa-109">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8bfa-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8bfa-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="f8bfa-110">See also</span></span>

- [<span data-ttu-id="f8bfa-111">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f8bfa-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
