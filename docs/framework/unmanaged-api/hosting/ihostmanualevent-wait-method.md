---
title: Método IHostManualEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
ms.openlocfilehash: 3fe8434ba4a7fc49b99bdf3084ce4f3981f25a9b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719821"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="d5652-102">Método IHostManualEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="d5652-102">IHostManualEvent::Wait Method</span></span>

<span data-ttu-id="d5652-103">Faz com que a instância [IHostManualEvent](ihostmanualevent-interface.md) atual aguarde até que ela seja propriedade ou um período de tempo especificado decorre.</span><span class="sxs-lookup"><span data-stu-id="d5652-103">Causes the current [IHostManualEvent](ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5652-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d5652-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5652-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d5652-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="d5652-106">no O número de milissegundos a aguardar antes de retornar, se a `IHostManualEvent` instância atual não pertence.</span><span class="sxs-lookup"><span data-stu-id="d5652-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="d5652-107">no Um dos valores de [WAIT_OPTION](wait-option-enumeration.md) , indicando a ação que o host deve executar se essa operação bloquear.</span><span class="sxs-lookup"><span data-stu-id="d5652-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5652-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="d5652-108">Return Value</span></span>  
  
|<span data-ttu-id="d5652-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5652-109">HRESULT</span></span>|<span data-ttu-id="d5652-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="d5652-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5652-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5652-111">S_OK</span></span>|<span data-ttu-id="d5652-112">`Wait` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="d5652-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="d5652-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5652-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5652-114">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="d5652-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d5652-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5652-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5652-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="d5652-116">The call timed out.</span></span>|  
|<span data-ttu-id="d5652-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5652-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5652-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="d5652-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5652-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5652-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5652-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="d5652-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5652-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5652-121">E_FAIL</span></span>|<span data-ttu-id="d5652-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="d5652-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5652-123">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="d5652-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5652-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d5652-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d5652-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="d5652-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="d5652-126">O host detectou um deadlock durante o intervalo de espera e escolheu a `IHostManualEvent` instância atual como a vítima do deadlock.</span><span class="sxs-lookup"><span data-stu-id="d5652-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5652-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5652-127">Requirements</span></span>  

 <span data-ttu-id="d5652-128">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5652-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5652-129">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d5652-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5652-130">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5652-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5652-131">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5652-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5652-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="d5652-132">See also</span></span>

- [<span data-ttu-id="d5652-133">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d5652-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d5652-134">Interface IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="d5652-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="d5652-135">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="d5652-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="d5652-136">Interface IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="d5652-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="d5652-137">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d5652-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
