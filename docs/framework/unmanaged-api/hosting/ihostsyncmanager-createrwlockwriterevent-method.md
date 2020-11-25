---
title: Método IHostSyncManager::CreateRWLockWriterEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
ms.openlocfilehash: 5b5faf14337f78d9b176787528ae8947f5810ba6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704364"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="7cca8-102">Método IHostSyncManager::CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="7cca8-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>

<span data-ttu-id="7cca8-103">Cria um objeto de evento de redefinição automática para a implementação de um bloqueio de gravador.</span><span class="sxs-lookup"><span data-stu-id="7cca8-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cca8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7cca8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cca8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7cca8-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="7cca8-106">no Um cookie a ser associado ao evento de redefinição automática.</span><span class="sxs-lookup"><span data-stu-id="7cca8-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="7cca8-107">fora Um ponteiro para o endereço de uma instância de [IHostAutoEvent](ihostautoevent-interface.md) ou NULL se o objeto de evento não pôde ser criado.</span><span class="sxs-lookup"><span data-stu-id="7cca8-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cca8-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="7cca8-108">Return Value</span></span>  
  
|<span data-ttu-id="7cca8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cca8-109">HRESULT</span></span>|<span data-ttu-id="7cca8-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="7cca8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7cca8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cca8-111">S_OK</span></span>|<span data-ttu-id="7cca8-112">`CreateRWLockWriterEvent` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="7cca8-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7cca8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7cca8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7cca8-114">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="7cca8-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7cca8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7cca8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7cca8-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="7cca8-116">The call timed out.</span></span>|  
|<span data-ttu-id="7cca8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7cca8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7cca8-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="7cca8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7cca8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7cca8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7cca8-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="7cca8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7cca8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7cca8-121">E_FAIL</span></span>|<span data-ttu-id="7cca8-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="7cca8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7cca8-123">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="7cca8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7cca8-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7cca8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7cca8-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7cca8-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7cca8-126">Não havia memória suficiente disponível para criar o objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="7cca8-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cca8-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="7cca8-127">Remarks</span></span>  

 <span data-ttu-id="7cca8-128">O CLR chama o `CreateRWLockWriterEvent` método para obter uma referência a uma `IHostAutoEvent` instância a ser usada em sua implementação de um bloqueio de gravador.</span><span class="sxs-lookup"><span data-stu-id="7cca8-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="7cca8-129">O host pode usar o cookie especificado para determinar quais tarefas estão aguardando no bloqueio chamando os métodos de iteração da interface [ICLRSyncManager](iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7cca8-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cca8-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cca8-130">Requirements</span></span>  

 <span data-ttu-id="7cca8-131">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cca8-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cca8-132">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7cca8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7cca8-133">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7cca8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cca8-134">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cca8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cca8-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="7cca8-135">See also</span></span>

- [<span data-ttu-id="7cca8-136">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7cca8-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="7cca8-137">Interface IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="7cca8-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="7cca8-138">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="7cca8-138">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="7cca8-139">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7cca8-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
