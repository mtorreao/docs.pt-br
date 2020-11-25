---
title: Método IHostSyncManager::CreateRWLockReaderEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
ms.openlocfilehash: 7c9bf2186d3dc4500694225ea4023df3609b9010
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704377"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="dae33-102">Método IHostSyncManager::CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="dae33-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>

<span data-ttu-id="dae33-103">Cria um objeto de evento de redefinição manual para a implementação de um bloqueio de leitor.</span><span class="sxs-lookup"><span data-stu-id="dae33-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae33-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dae33-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dae33-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dae33-105">Parameters</span></span>  

 `bInitialState`  
 <span data-ttu-id="dae33-106">[in] `true` , se `ppEvent` deve ser sinalizado; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="dae33-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="dae33-107">no Um cookie a ser associado ao bloqueio do leitor.</span><span class="sxs-lookup"><span data-stu-id="dae33-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="dae33-108">fora Um ponteiro para o endereço de uma instância de [IHostManualEvent](ihostmanualevent-interface.md) ou NULL se o objeto de evento não pôde ser criado.</span><span class="sxs-lookup"><span data-stu-id="dae33-108">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dae33-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="dae33-109">Return Value</span></span>  
  
|<span data-ttu-id="dae33-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dae33-110">HRESULT</span></span>|<span data-ttu-id="dae33-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="dae33-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dae33-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="dae33-112">S_OK</span></span>|<span data-ttu-id="dae33-113">`CreateRWLockReaderEvent` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="dae33-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="dae33-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dae33-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dae33-115">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="dae33-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dae33-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dae33-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dae33-117">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="dae33-117">The call timed out.</span></span>|  
|<span data-ttu-id="dae33-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dae33-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dae33-119">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="dae33-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dae33-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dae33-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dae33-121">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="dae33-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dae33-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dae33-122">E_FAIL</span></span>|<span data-ttu-id="dae33-123">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="dae33-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dae33-124">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="dae33-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dae33-125">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dae33-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dae33-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dae33-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dae33-127">Não havia memória suficiente disponível para criar o objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="dae33-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dae33-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="dae33-128">Remarks</span></span>  

 <span data-ttu-id="dae33-129">O CLR chama `CreateRWLockReaderEvent` para obter uma referência a uma `IHostManualEvent` instância a ser usada na implementação de um bloqueio de leitor.</span><span class="sxs-lookup"><span data-stu-id="dae33-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="dae33-130">O host pode usar o cookie para determinar quais tarefas estão aguardando no bloqueio do leitor consultando a interface [ICLRSyncManager](iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dae33-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dae33-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dae33-131">Requirements</span></span>  

 <span data-ttu-id="dae33-132">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dae33-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dae33-133">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dae33-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dae33-134">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dae33-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dae33-135">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dae33-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae33-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="dae33-136">See also</span></span>

- [<span data-ttu-id="dae33-137">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="dae33-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="dae33-138">Interface IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="dae33-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="dae33-139">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="dae33-139">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="dae33-140">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="dae33-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
