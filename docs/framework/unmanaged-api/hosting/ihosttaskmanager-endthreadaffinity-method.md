---
title: Método IHostTaskManager::EndThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: c662e242cf6745223b1e87716ce4f64971347d2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731651"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="bbe0a-102">Método IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="bbe0a-102">IHostTaskManager::EndThreadAffinity Method</span></span>

<span data-ttu-id="bbe0a-103">Notifica o host de que o código gerenciado está saindo do período no qual a tarefa atual não deve ser movida para outro thread do sistema operacional, seguindo uma chamada anterior para [IHostTaskManager:: BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="bbe0a-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe0a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bbe0a-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bbe0a-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="bbe0a-105">Return Value</span></span>  
  
|<span data-ttu-id="bbe0a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bbe0a-106">HRESULT</span></span>|<span data-ttu-id="bbe0a-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="bbe0a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bbe0a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="bbe0a-108">S_OK</span></span>|<span data-ttu-id="bbe0a-109">`EndThreadAffinity` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="bbe0a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bbe0a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bbe0a-111">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bbe0a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bbe0a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bbe0a-113">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-113">The call timed out.</span></span>|  
|<span data-ttu-id="bbe0a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bbe0a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bbe0a-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bbe0a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bbe0a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bbe0a-117">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bbe0a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bbe0a-118">E_FAIL</span></span>|<span data-ttu-id="bbe0a-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bbe0a-120">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bbe0a-121">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bbe0a-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="bbe0a-122">E_UNEXPECTED</span></span>|<span data-ttu-id="bbe0a-123">`EndThreadAffinity` foi chamado sem uma chamada correspondente anterior para `BeginThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="bbe0a-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbe0a-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="bbe0a-124">Remarks</span></span>  

 <span data-ttu-id="bbe0a-125">O CLR faz uma chamada correspondente para `BeginThreadAffinity` na tarefa atual antes de chamar `EndThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="bbe0a-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="bbe0a-126">Na ausência de tal chamada correspondente, a implementação do host de [IHostTaskManager](ihosttaskmanager-interface.md) deve retornar E_UNEXPECTED e não tomar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="bbe0a-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbe0a-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbe0a-127">Requirements</span></span>  

 <span data-ttu-id="bbe0a-128">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbe0a-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbe0a-129">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bbe0a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bbe0a-130">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bbe0a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bbe0a-131">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbe0a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe0a-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="bbe0a-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="bbe0a-133">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="bbe0a-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="bbe0a-134">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="bbe0a-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="bbe0a-135">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="bbe0a-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="bbe0a-136">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="bbe0a-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
