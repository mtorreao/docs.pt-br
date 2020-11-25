---
title: Método IHostThreadPoolManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
ms.openlocfilehash: 54dfa2741d3b4c1b2eada75ee8d214a2d0b250a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730765"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="2588c-102">Método IHostThreadPoolManager::GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="2588c-102">IHostThreadPoolManager::GetMinThreads Method</span></span>

<span data-ttu-id="2588c-103">Obtém o número mínimo de threads ociosos que o host mantém no pool de threads, em previsão de solicitações.</span><span class="sxs-lookup"><span data-stu-id="2588c-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2588c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2588c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2588c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2588c-105">Parameters</span></span>  

 `MinThreads`  
 <span data-ttu-id="2588c-106">fora Um ponteiro para o número mínimo de threads de trabalho ociosos que o host mantém atualmente.</span><span class="sxs-lookup"><span data-stu-id="2588c-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2588c-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="2588c-107">Return Value</span></span>  
  
|<span data-ttu-id="2588c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2588c-108">HRESULT</span></span>|<span data-ttu-id="2588c-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="2588c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2588c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2588c-110">S_OK</span></span>|<span data-ttu-id="2588c-111">`GetMinThreads` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="2588c-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="2588c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2588c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2588c-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="2588c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2588c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2588c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2588c-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="2588c-115">The call timed out.</span></span>|  
|<span data-ttu-id="2588c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2588c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2588c-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="2588c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2588c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2588c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2588c-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="2588c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2588c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2588c-120">E_FAIL</span></span>|<span data-ttu-id="2588c-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="2588c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2588c-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="2588c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2588c-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2588c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2588c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2588c-124">E_NOTIMPL</span></span>|<span data-ttu-id="2588c-125">O host não fornece uma implementação de `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="2588c-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2588c-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="2588c-126">Remarks</span></span>  

 <span data-ttu-id="2588c-127">O host não é necessário para fornecer uma implementação do `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="2588c-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="2588c-128">Nesse caso, ele deve retornar um valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="2588c-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2588c-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2588c-129">Requirements</span></span>  

 <span data-ttu-id="2588c-130">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2588c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2588c-131">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2588c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2588c-132">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2588c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2588c-133">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2588c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2588c-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="2588c-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="2588c-135">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="2588c-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="2588c-136">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="2588c-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="2588c-137">Interface IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="2588c-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
