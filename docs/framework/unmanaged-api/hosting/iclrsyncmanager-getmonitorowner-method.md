---
title: Método ICLRSyncManager::GetMonitorOwner
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
ms.openlocfilehash: a2cb82d8071518af4d4bc3276871f3846a5a5693
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687061"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="53179-102">Método ICLRSyncManager::GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="53179-102">ICLRSyncManager::GetMonitorOwner Method</span></span>

<span data-ttu-id="53179-103">Obtém a instância de [IHostTask](ihosttask-interface.md) que possui o monitor identificado pelo cookie especificado.</span><span class="sxs-lookup"><span data-stu-id="53179-103">Gets the [IHostTask](ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53179-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="53179-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53179-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="53179-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="53179-106">no O cookie associado ao monitor.</span><span class="sxs-lookup"><span data-stu-id="53179-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="53179-107">fora Um ponteiro para o `IHostTask` que atualmente possui o monitor ou nulo se nenhuma tarefa tiver propriedade.</span><span class="sxs-lookup"><span data-stu-id="53179-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53179-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="53179-108">Return Value</span></span>  
  
|<span data-ttu-id="53179-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53179-109">HRESULT</span></span>|<span data-ttu-id="53179-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="53179-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53179-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="53179-111">S_OK</span></span>|<span data-ttu-id="53179-112">`GetMonitorOwner` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="53179-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="53179-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53179-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53179-114">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="53179-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="53179-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53179-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53179-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="53179-116">The call timed out.</span></span>|  
|<span data-ttu-id="53179-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53179-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53179-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="53179-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53179-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53179-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53179-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="53179-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53179-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53179-121">E_FAIL</span></span>|<span data-ttu-id="53179-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="53179-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53179-123">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="53179-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53179-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="53179-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53179-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="53179-125">Remarks</span></span>  

 <span data-ttu-id="53179-126">O host normalmente chama `GetMonitorOwner` como parte de um mecanismo de detecção de deadlock.</span><span class="sxs-lookup"><span data-stu-id="53179-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="53179-127">O cookie é associado a um monitor quando ele é criado usando uma chamada para [IHostSyncManager:: CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="53179-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53179-128">Uma chamada para liberar o evento subjacente ao monitor pode bloquear — mas não trava — se uma chamada para esse método estiver atualmente em vigor no cookie associado a esse monitor.</span><span class="sxs-lookup"><span data-stu-id="53179-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="53179-129">Outras tarefas também podem bloquear se tentarem adquirir esse monitor.</span><span class="sxs-lookup"><span data-stu-id="53179-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="53179-130">`GetMonitorOwner` sempre retorna imediatamente e pode ser chamado a qualquer momento após uma chamada para `CreateMonitorEvent` .</span><span class="sxs-lookup"><span data-stu-id="53179-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="53179-131">O host não precisa aguardar até que uma tarefa esteja aguardando o evento.</span><span class="sxs-lookup"><span data-stu-id="53179-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53179-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53179-132">Requirements</span></span>  

 <span data-ttu-id="53179-133">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53179-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53179-134">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53179-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53179-135">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53179-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53179-136">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53179-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53179-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="53179-137">See also</span></span>

- [<span data-ttu-id="53179-138">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="53179-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="53179-139">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="53179-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
