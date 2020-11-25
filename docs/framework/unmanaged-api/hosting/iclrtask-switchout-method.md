---
title: Método ICLRTask::SwitchOut
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: 1b27983b3f10eba225442dcd2f5df02062e53ed4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720263"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="5de64-102">Método ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="5de64-102">ICLRTask::SwitchOut Method</span></span>

<span data-ttu-id="5de64-103">Notifica o Common Language Runtime (CLR) que a tarefa representada pela instância [ICLRTask](iclrtask-interface.md) atual não está mais em um estado operável.</span><span class="sxs-lookup"><span data-stu-id="5de64-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de64-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5de64-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5de64-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="5de64-105">Return Value</span></span>  
  
|<span data-ttu-id="5de64-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5de64-106">HRESULT</span></span>|<span data-ttu-id="5de64-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="5de64-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5de64-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5de64-108">S_OK</span></span>|<span data-ttu-id="5de64-109">`SwitchOut` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="5de64-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="5de64-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5de64-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5de64-111">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="5de64-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5de64-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5de64-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5de64-113">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="5de64-113">The call timed out.</span></span>|  
|<span data-ttu-id="5de64-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5de64-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5de64-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="5de64-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5de64-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5de64-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5de64-117">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="5de64-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5de64-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5de64-118">E_FAIL</span></span>|<span data-ttu-id="5de64-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="5de64-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5de64-120">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="5de64-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5de64-121">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5de64-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5de64-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="5de64-122">Remarks</span></span>  

 <span data-ttu-id="5de64-123">Um host chama `SwitchOut` para informar ao CLR que ele interrompeu temporariamente a execução da tarefa que a `ICLRTask` instância atual representa e reagendará a tarefa.</span><span class="sxs-lookup"><span data-stu-id="5de64-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de64-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5de64-124">Requirements</span></span>  

 <span data-ttu-id="5de64-125">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5de64-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de64-126">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5de64-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5de64-127">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5de64-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5de64-128">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de64-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de64-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="5de64-129">See also</span></span>

- [<span data-ttu-id="5de64-130">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5de64-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5de64-131">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5de64-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5de64-132">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="5de64-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5de64-133">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5de64-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
