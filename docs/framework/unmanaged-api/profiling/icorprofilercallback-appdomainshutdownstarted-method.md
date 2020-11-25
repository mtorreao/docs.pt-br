---
title: Método ICorProfilerCallback::AppDomainShutdownStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: cb0b763059c787b8f3e93e6c46b0e7fb2f8f8b2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718456"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="7ae24-102">Método ICorProfilerCallback::AppDomainShutdownStarted</span><span class="sxs-lookup"><span data-stu-id="7ae24-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>

<span data-ttu-id="7ae24-103">Notifica o criador de perfil de que um domínio de aplicativo está sendo descarregado de um processo.</span><span class="sxs-lookup"><span data-stu-id="7ae24-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae24-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7ae24-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ae24-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7ae24-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="7ae24-106">\[in] identifica o domínio no qual os assemblies do aplicativo são armazenados.</span><span class="sxs-lookup"><span data-stu-id="7ae24-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ae24-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="7ae24-107">Remarks</span></span>  

 <span data-ttu-id="7ae24-108">O valor de `appDomainId` não é válido para nenhuma solicitação de informações após o `AppDomainShutdownStarted` retorno do método — essa é a última chance do criador de perfil obter informações sobre esse domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7ae24-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae24-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ae24-109">Requirements</span></span>  

 <span data-ttu-id="7ae24-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ae24-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae24-111">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="7ae24-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ae24-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ae24-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ae24-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae24-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae24-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="7ae24-114">See also</span></span>

- [<span data-ttu-id="7ae24-115">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7ae24-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
