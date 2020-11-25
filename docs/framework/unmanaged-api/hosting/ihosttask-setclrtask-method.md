---
title: Método IHostTask::SetCLRTask
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: e6b9a4015a6139d6c8d7101fa7811c7ad9134e4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720458"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="971ef-102">Método IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="971ef-102">IHostTask::SetCLRTask Method</span></span>

<span data-ttu-id="971ef-103">Associa uma `ICLRTask` instância à instância de [IHostTask](ihosttask-interface.md) atual.</span><span class="sxs-lookup"><span data-stu-id="971ef-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="971ef-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="971ef-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="971ef-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="971ef-105">Parameters</span></span>  

 `pCLRTask`  
 <span data-ttu-id="971ef-106">no Um ponteiro de interface para a `ICLRTask` instância a ser associada à `IHostTask` instância atual.</span><span class="sxs-lookup"><span data-stu-id="971ef-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="971ef-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="971ef-107">Return Value</span></span>  
  
|<span data-ttu-id="971ef-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="971ef-108">HRESULT</span></span>|<span data-ttu-id="971ef-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="971ef-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="971ef-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="971ef-110">S_OK</span></span>|<span data-ttu-id="971ef-111">`SetCLRTask` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="971ef-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="971ef-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="971ef-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="971ef-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="971ef-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="971ef-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="971ef-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="971ef-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="971ef-115">The call timed out.</span></span>|  
|<span data-ttu-id="971ef-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="971ef-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="971ef-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="971ef-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="971ef-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="971ef-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="971ef-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="971ef-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="971ef-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="971ef-120">E_FAIL</span></span>|<span data-ttu-id="971ef-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="971ef-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="971ef-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="971ef-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="971ef-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="971ef-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="971ef-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="971ef-124">Remarks</span></span>  

 <span data-ttu-id="971ef-125">O CLR chama `SetCLRTask` para associar uma `ICLRTask` instância à instância atual `IHostTask` , que foi criada por uma chamada para [IHostTaskManager:: CreateTask](ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="971ef-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="971ef-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="971ef-126">Requirements</span></span>  

 <span data-ttu-id="971ef-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="971ef-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="971ef-128">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="971ef-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="971ef-129">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="971ef-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="971ef-130">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="971ef-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="971ef-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="971ef-131">See also</span></span>

- [<span data-ttu-id="971ef-132">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="971ef-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="971ef-133">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="971ef-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="971ef-134">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="971ef-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="971ef-135">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="971ef-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
