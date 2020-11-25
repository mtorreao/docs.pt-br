---
title: Método IHostTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
ms.openlocfilehash: 72b7f6e3a5a09bd06e8a7fbb94680ed3ea89b225
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727296"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="9ecb8-102">Método IHostTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="9ecb8-102">IHostTaskManager::GetCurrentTask Method</span></span>

<span data-ttu-id="9ecb8-103">Obtém um ponteiro de interface para a tarefa que está atualmente em execução no thread do sistema operacional do qual essa chamada é feita.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ecb8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ecb8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ecb8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9ecb8-105">Parameters</span></span>  

 `pTask`  
 <span data-ttu-id="9ecb8-106">fora Um ponteiro para o endereço de uma instância de [IHostTask](ihosttask-interface.md) que representa a tarefa em execução no momento, ou NULL, se nenhuma tarefa estiver em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-106">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ecb8-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="9ecb8-107">Return Value</span></span>  
  
|<span data-ttu-id="9ecb8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ecb8-108">HRESULT</span></span>|<span data-ttu-id="9ecb8-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="9ecb8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ecb8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ecb8-110">S_OK</span></span>|<span data-ttu-id="9ecb8-111">`GetCurrentTask` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="9ecb8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ecb8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ecb8-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ecb8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ecb8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ecb8-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-115">The call timed out.</span></span>|  
|<span data-ttu-id="9ecb8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ecb8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ecb8-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ecb8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ecb8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ecb8-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ecb8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ecb8-120">E_FAIL</span></span>|<span data-ttu-id="9ecb8-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ecb8-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ecb8-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9ecb8-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="9ecb8-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="9ecb8-125">`GetCurrentTask` foi chamado em um thread do sistema operacional fora do controle do host.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ecb8-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="9ecb8-126">Remarks</span></span>  

 <span data-ttu-id="9ecb8-127">O host também pode definir o `pTask` parâmetro como nulo para impedir que uma tarefa que não foi iniciada Insira o CLR.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ecb8-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ecb8-128">Requirements</span></span>  

 <span data-ttu-id="9ecb8-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ecb8-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ecb8-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9ecb8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ecb8-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ecb8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ecb8-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ecb8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecb8-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="9ecb8-133">See also</span></span>

- [<span data-ttu-id="9ecb8-134">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="9ecb8-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="9ecb8-135">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9ecb8-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="9ecb8-136">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="9ecb8-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="9ecb8-137">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="9ecb8-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
