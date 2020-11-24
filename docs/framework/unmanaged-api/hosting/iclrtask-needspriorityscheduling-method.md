---
title: Método ICLRTask::NeedsPriorityScheduling
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
ms.openlocfilehash: 86e0899b883f09f2e7b27c0f957e943deb73bb66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690792"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="dd0d5-102">Método ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="dd0d5-102">ICLRTask::NeedsPriorityScheduling Method</span></span>

<span data-ttu-id="dd0d5-103">Obtém um valor que indica se a tarefa atual, que está sendo desativada, precisa ser marcada como uma prioridade alta para reagendar.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd0d5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd0d5-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd0d5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dd0d5-105">Parameters</span></span>  

 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="dd0d5-106">[fora] `true` , se o host deve tentar reagendar a instância de tarefa atual assim que possível; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="dd0d5-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd0d5-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="dd0d5-107">Return Value</span></span>  
  
|<span data-ttu-id="dd0d5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd0d5-108">HRESULT</span></span>|<span data-ttu-id="dd0d5-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd0d5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd0d5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd0d5-110">S_OK</span></span>|<span data-ttu-id="dd0d5-111">`NeedsPriorityRescheduling` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="dd0d5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd0d5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd0d5-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd0d5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd0d5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd0d5-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-115">The call timed out.</span></span>|  
|<span data-ttu-id="dd0d5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd0d5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd0d5-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd0d5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd0d5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd0d5-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd0d5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd0d5-120">E_FAIL</span></span>|<span data-ttu-id="dd0d5-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd0d5-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd0d5-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd0d5-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd0d5-124">Remarks</span></span>  

 <span data-ttu-id="dd0d5-125">Em situações em que a tarefa está próxima de ser coletada pelo coletor de lixo, o CLR define o valor de `pbNeedsPriorityScheduling` como `true` , indicando reagendamento de alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="dd0d5-126">Isso permite que o host reagende a tarefa rapidamente, minimizando assim o potencial de atrasos na coleta de lixo e permitindo que o host e o tempo de execução cooperam em conservar recursos de memória.</span><span class="sxs-lookup"><span data-stu-id="dd0d5-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd0d5-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd0d5-127">Requirements</span></span>  

 <span data-ttu-id="dd0d5-128">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd0d5-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd0d5-129">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dd0d5-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd0d5-130">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd0d5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd0d5-131">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd0d5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd0d5-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="dd0d5-132">See also</span></span>

- [<span data-ttu-id="dd0d5-133">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="dd0d5-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="dd0d5-134">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd0d5-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="dd0d5-135">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="dd0d5-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="dd0d5-136">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd0d5-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
