---
title: Método IHostSemaphore::ReleaseSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
ms.openlocfilehash: 660062fb69bb8fe0a06bbca9046d65175fb72f9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683024"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="e2280-102">Método IHostSemaphore::ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="e2280-102">IHostSemaphore::ReleaseSemaphore Method</span></span>

<span data-ttu-id="e2280-103">Aumenta a contagem da instância de [IHostSemaphore](ihostsemaphore-interface.md) atual pelo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="e2280-103">Increases the count of the current [IHostSemaphore](ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2280-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e2280-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2280-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e2280-105">Parameters</span></span>  

 `lReleaseCount`  
 <span data-ttu-id="e2280-106">no O valor pelo qual aumentar a contagem da `IHostSemaphore` instância atual.</span><span class="sxs-lookup"><span data-stu-id="e2280-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="e2280-107">Essa quantidade deve ser maior que zero.</span><span class="sxs-lookup"><span data-stu-id="e2280-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="e2280-108">fora Um ponteiro para a contagem anterior ou NULL se o chamador não exigir a contagem anterior.</span><span class="sxs-lookup"><span data-stu-id="e2280-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2280-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="e2280-109">Return Value</span></span>  
  
|<span data-ttu-id="e2280-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2280-110">HRESULT</span></span>|<span data-ttu-id="e2280-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="e2280-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2280-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2280-112">S_OK</span></span>|<span data-ttu-id="e2280-113">`ReleaseSemaphore` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="e2280-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="e2280-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2280-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2280-115">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="e2280-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e2280-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e2280-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e2280-117">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="e2280-117">The call timed out.</span></span>|  
|<span data-ttu-id="e2280-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e2280-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e2280-119">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="e2280-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e2280-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e2280-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e2280-121">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="e2280-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e2280-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2280-122">E_FAIL</span></span>|<span data-ttu-id="e2280-123">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="e2280-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e2280-124">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="e2280-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e2280-125">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e2280-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2280-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="e2280-126">Remarks</span></span>  

 <span data-ttu-id="e2280-127">O CLR normalmente chama `ReleaseSemaphore` para notificar o host de que ele concluiu o uso de um recurso, passando um valor de 1 para o `lReleaseCount` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e2280-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2280-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2280-128">Requirements</span></span>  

 <span data-ttu-id="e2280-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2280-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2280-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2280-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2280-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2280-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2280-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2280-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2280-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="e2280-133">See also</span></span>

- [<span data-ttu-id="e2280-134">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="e2280-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="e2280-135">Interface IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="e2280-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="e2280-136">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="e2280-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="e2280-137">Interface IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="e2280-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="e2280-138">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="e2280-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
