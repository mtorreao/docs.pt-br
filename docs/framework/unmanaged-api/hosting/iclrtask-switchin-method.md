---
title: Método ICLRTask::SwitchIn
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: e98ae17d55c74d32844da96137c258d076ebc2db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691047"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="84459-102">Método ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="84459-102">ICLRTask::SwitchIn Method</span></span>

<span data-ttu-id="84459-103">Notifica o Common Language Runtime (CLR) que a tarefa que a instância [ICLRTask](iclrtask-interface.md) atual representa agora está em um estado operável.</span><span class="sxs-lookup"><span data-stu-id="84459-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84459-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="84459-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84459-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="84459-105">Parameters</span></span>  

 `threadHandle`  
 <span data-ttu-id="84459-106">no Um identificador para o thread físico no qual a tarefa representada pela instância atual `ICLRTask` está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="84459-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84459-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="84459-107">Return Value</span></span>  
  
|<span data-ttu-id="84459-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84459-108">HRESULT</span></span>|<span data-ttu-id="84459-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="84459-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84459-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="84459-110">S_OK</span></span>|<span data-ttu-id="84459-111">`SwitchIn` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="84459-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="84459-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84459-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84459-113">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="84459-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84459-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84459-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84459-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="84459-115">The call timed out.</span></span>|  
|<span data-ttu-id="84459-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84459-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84459-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="84459-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84459-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84459-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84459-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="84459-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84459-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84459-120">E_FAIL</span></span>|<span data-ttu-id="84459-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="84459-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84459-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="84459-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84459-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="84459-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="84459-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="84459-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="84459-125">`SwitchIn` foi chamado sem uma chamada anterior para o [método SwitchOut](iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="84459-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84459-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="84459-126">Remarks</span></span>  

 <span data-ttu-id="84459-127">O `threadHandle` parâmetro representa um identificador para o thread do sistema operacional no qual a tarefa representada pela instância atual foi `ICLRTask` agendada.</span><span class="sxs-lookup"><span data-stu-id="84459-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="84459-128">Se a representação tiver ocorrido neste thread, você deverá chamar [IHostSecurityManager:: RevertToSelf](ihostsecuritymanager-reverttoself-method.md) antes de alternar para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="84459-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84459-129">Uma chamada para `SwitchIn` sem uma chamada anterior para `SwitchOut` falha com um valor HRESULT de HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="84459-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84459-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84459-130">Requirements</span></span>  

 <span data-ttu-id="84459-131">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84459-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84459-132">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84459-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84459-133">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84459-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84459-134">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84459-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84459-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="84459-135">See also</span></span>

- [<span data-ttu-id="84459-136">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="84459-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="84459-137">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="84459-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="84459-138">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="84459-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="84459-139">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="84459-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
