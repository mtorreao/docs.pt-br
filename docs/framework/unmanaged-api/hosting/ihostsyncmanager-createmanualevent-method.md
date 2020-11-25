---
title: Método IHostSyncManager::CreateManualEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 67af8f125b2be39138bac5d51148215f3a3acf86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723864"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="779b4-102">Método IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="779b4-102">IHostSyncManager::CreateManualEvent Method</span></span>

<span data-ttu-id="779b4-103">Cria um objeto de evento de redefinição manual.</span><span class="sxs-lookup"><span data-stu-id="779b4-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="779b4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="779b4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="779b4-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="779b4-105">Parameters</span></span>  

 `bInitialState`  
 <span data-ttu-id="779b4-106">[in] `true` , se o objeto for sinalizado; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="779b4-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="779b4-107">fora Um ponteiro para o endereço de uma instância de [IHostManualEvent](ihostmanualevent-interface.md) ou NULL se o evento não pôde ser criado.</span><span class="sxs-lookup"><span data-stu-id="779b4-107">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="779b4-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="779b4-108">Return Value</span></span>  
  
|<span data-ttu-id="779b4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="779b4-109">HRESULT</span></span>|<span data-ttu-id="779b4-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="779b4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="779b4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="779b4-111">S_OK</span></span>|<span data-ttu-id="779b4-112">`CreateManualEvent` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="779b4-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="779b4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="779b4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="779b4-114">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="779b4-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="779b4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="779b4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="779b4-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="779b4-116">The call timed out.</span></span>|  
|<span data-ttu-id="779b4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="779b4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="779b4-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="779b4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="779b4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="779b4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="779b4-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="779b4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="779b4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="779b4-121">E_FAIL</span></span>|<span data-ttu-id="779b4-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="779b4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="779b4-123">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="779b4-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="779b4-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="779b4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="779b4-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="779b4-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="779b4-126">Não havia memória suficiente disponível para criar o objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="779b4-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="779b4-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="779b4-127">Remarks</span></span>  

 <span data-ttu-id="779b4-128">`CreateManualEvent` Cria um `IHostManualEvent` , um objeto de evento de redefinição manual que requer uma chamada para o método [IHostManualEvent:: Reset](ihostmanualevent-reset-method.md) para defini-lo como um estado não sinalizado.</span><span class="sxs-lookup"><span data-stu-id="779b4-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="779b4-129">`CreateManualEvent` espelha a função do Win32 `CreateEvent` com um valor de `true` especificado para o `bManualReset` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="779b4-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="779b4-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="779b4-130">Requirements</span></span>  

 <span data-ttu-id="779b4-131">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="779b4-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="779b4-132">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="779b4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="779b4-133">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="779b4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="779b4-134">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="779b4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="779b4-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="779b4-135">See also</span></span>

- [<span data-ttu-id="779b4-136">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="779b4-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="779b4-137">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="779b4-137">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="779b4-138">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="779b4-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
