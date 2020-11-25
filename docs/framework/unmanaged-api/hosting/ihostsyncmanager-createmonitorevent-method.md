---
title: Método IHostSyncManager::CreateMonitorEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: 7fc431861ac8f5c0e47e12e688f4ca004313c062
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704429"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="3e876-102">Método IHostSyncManager::CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="3e876-102">IHostSyncManager::CreateMonitorEvent Method</span></span>

<span data-ttu-id="3e876-103">Cria um objeto de evento monitorado de redefinição automática.</span><span class="sxs-lookup"><span data-stu-id="3e876-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e876-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3e876-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e876-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3e876-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="3e876-106">no Um cookie a ser associado ao objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="3e876-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="3e876-107">fora Um ponteiro para o endereço de uma instância de [IHostAutoEvent](ihostautoevent-interface.md) ou NULL se o objeto de evento não pôde ser criado.</span><span class="sxs-lookup"><span data-stu-id="3e876-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e876-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="3e876-108">Return Value</span></span>  
  
|<span data-ttu-id="3e876-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e876-109">HRESULT</span></span>|<span data-ttu-id="3e876-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="3e876-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e876-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e876-111">S_OK</span></span>|<span data-ttu-id="3e876-112">`CreateMonitorEvent` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="3e876-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="3e876-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e876-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e876-114">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="3e876-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e876-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e876-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e876-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="3e876-116">The call timed out.</span></span>|  
|<span data-ttu-id="3e876-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e876-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e876-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="3e876-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e876-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e876-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e876-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="3e876-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e876-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e876-121">E_FAIL</span></span>|<span data-ttu-id="3e876-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="3e876-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e876-123">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="3e876-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e876-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3e876-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3e876-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3e876-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3e876-126">Não havia memória suficiente disponível para criar o objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="3e876-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e876-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="3e876-127">Remarks</span></span>  

 <span data-ttu-id="3e876-128">`CreateMonitorEvent` Retorna um `IHostAutoEvent` que o CLR usa em sua implementação do tipo gerenciado <xref:System.Threading.Monitor?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3e876-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="3e876-129">Esse método espelha a função do Win32 `CreateEvent` , com um valor de `false` especificado para o `bManualReset` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3e876-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="3e876-130">O host pode usar o cookie para determinar qual tarefa está aguardando no monitor chamando o método [ICLRSyncManager:: GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3e876-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e876-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e876-131">Requirements</span></span>  

 <span data-ttu-id="3e876-132">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e876-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e876-133">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3e876-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e876-134">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e876-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e876-135">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e876-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e876-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="3e876-136">See also</span></span>

- [<span data-ttu-id="3e876-137">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="3e876-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="3e876-138">Interface IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="3e876-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="3e876-139">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="3e876-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
