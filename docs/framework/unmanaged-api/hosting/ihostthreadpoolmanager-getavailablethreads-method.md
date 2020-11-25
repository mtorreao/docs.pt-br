---
title: Método IHostThreadPoolManager::GetAvailableThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 64d5ba9ad5557f99b175c277d48003529d77861c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730793"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="ad290-102">Método IHostThreadPoolManager::GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="ad290-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="ad290-103">Obtém o número de threads no pool de threads que não estão processando itens de trabalho no momento.</span><span class="sxs-lookup"><span data-stu-id="ad290-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad290-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ad290-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad290-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ad290-105">Parameters</span></span>  

 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="ad290-106">fora Ponteiro para o número de threads no pool de threads que não estão processando itens de trabalho no momento.</span><span class="sxs-lookup"><span data-stu-id="ad290-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad290-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="ad290-107">Return Value</span></span>  
  
|<span data-ttu-id="ad290-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad290-108">HRESULT</span></span>|<span data-ttu-id="ad290-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="ad290-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad290-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad290-110">S_OK</span></span>|<span data-ttu-id="ad290-111">`GetAvailableThreads` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="ad290-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ad290-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ad290-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ad290-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="ad290-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ad290-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ad290-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ad290-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="ad290-115">The call timed out.</span></span>|  
|<span data-ttu-id="ad290-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ad290-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ad290-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="ad290-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ad290-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ad290-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ad290-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="ad290-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ad290-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ad290-120">E_FAIL</span></span>|<span data-ttu-id="ad290-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="ad290-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ad290-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="ad290-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ad290-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ad290-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ad290-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ad290-124">E_NOTIMPL</span></span>|<span data-ttu-id="ad290-125">O host não fornece uma implementação de `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="ad290-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad290-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="ad290-126">Remarks</span></span>  

 <span data-ttu-id="ad290-127">Se o host não fornecer uma implementação de `GetAvailableThreads` , ele deverá retornar um valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ad290-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad290-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad290-128">Requirements</span></span>  

 <span data-ttu-id="ad290-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad290-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad290-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ad290-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad290-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad290-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad290-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad290-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad290-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="ad290-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="ad290-134">Interface IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="ad290-134">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
