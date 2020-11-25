---
title: Método IHostGCManager::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
ms.openlocfilehash: 9120085f6a241bcda04946a843799987bf82bb84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723877"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="88288-102">Método IHostGCManager::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="88288-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="88288-103">Notifica o host de que o thread do qual a chamada de método foi feita está prestes a ser bloqueado para uma coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="88288-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88288-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="88288-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="88288-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="88288-105">Return Value</span></span>  
  
|<span data-ttu-id="88288-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88288-106">HRESULT</span></span>|<span data-ttu-id="88288-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="88288-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88288-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="88288-108">S_OK</span></span>|<span data-ttu-id="88288-109">`ThreadIsBlockingForSuspension` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="88288-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="88288-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="88288-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="88288-111">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="88288-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="88288-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="88288-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="88288-113">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="88288-113">The call timed out.</span></span>|  
|<span data-ttu-id="88288-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="88288-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="88288-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="88288-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="88288-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="88288-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="88288-117">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="88288-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="88288-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="88288-118">E_FAIL</span></span>|<span data-ttu-id="88288-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="88288-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="88288-120">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="88288-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="88288-121">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="88288-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88288-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="88288-122">Remarks</span></span>  

 <span data-ttu-id="88288-123">O CLR normalmente chama o `ThreadIsBlockForSuspension` método em preparação para uma coleta de lixo, para dar ao host uma oportunidade de reagendar o thread para tarefas não gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="88288-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="88288-124">O host pode reagendar tarefas somente após uma chamada para `ThreadIsBlockingForSuspension` .</span><span class="sxs-lookup"><span data-stu-id="88288-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="88288-125">Depois que o tempo de execução chama [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), o host não deve reagendar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="88288-125">After the runtime calls [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88288-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88288-126">Requirements</span></span>  

 <span data-ttu-id="88288-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88288-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88288-128">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="88288-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88288-129">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88288-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88288-130">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88288-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88288-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="88288-131">See also</span></span>

- [<span data-ttu-id="88288-132">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="88288-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="88288-133">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="88288-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="88288-134">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="88288-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="88288-135">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="88288-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="88288-136">Interface IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="88288-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
