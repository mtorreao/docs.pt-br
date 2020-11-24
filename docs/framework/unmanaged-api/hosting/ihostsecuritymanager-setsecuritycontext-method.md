---
title: Método IHostSecurityManager::SetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: dadacaea2b8741afc7b8c51404e2604dc759a629
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680372"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="a8ee6-102">Método IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="a8ee6-102">IHostSecurityManager::SetSecurityContext Method</span></span>

<span data-ttu-id="a8ee6-103">Define o contexto de segurança do thread atualmente em execução.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8ee6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a8ee6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8ee6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a8ee6-105">Parameters</span></span>  

 `eContextType`  
 <span data-ttu-id="a8ee6-106">no Um dos valores de [EContextType](econtexttype-enumeration.md) , indicando que tipo de contexto o Common Language Runtime (CLR) está colocando no host.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="a8ee6-107">fora Um ponteiro para o endereço de um novo objeto [IHostSecurityContext](ihostsecuritycontext-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a8ee6-107">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8ee6-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="a8ee6-108">Return Value</span></span>  
  
|<span data-ttu-id="a8ee6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8ee6-109">HRESULT</span></span>|<span data-ttu-id="a8ee6-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="a8ee6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8ee6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8ee6-111">S_OK</span></span>|<span data-ttu-id="a8ee6-112">`SetSecurityContext` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="a8ee6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a8ee6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a8ee6-114">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a8ee6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a8ee6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a8ee6-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-116">The call timed out.</span></span>|  
|<span data-ttu-id="a8ee6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a8ee6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a8ee6-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a8ee6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a8ee6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a8ee6-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a8ee6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a8ee6-121">E_FAIL</span></span>|<span data-ttu-id="a8ee6-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a8ee6-123">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a8ee6-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8ee6-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="a8ee6-125">Remarks</span></span>  

 <span data-ttu-id="a8ee6-126">O CLR chama `SetSecurityContext` em vários cenários.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="a8ee6-127">Antes de executar construtores de classe e de módulo e finalizadores, as chamadas de CLR `SetSecurityContext` para proteger o host contra falhas de execução.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="a8ee6-128">Em seguida, ele redefine o contexto de segurança para seu estado original após a execução do construtor ou finalizador, usando outra chamada para `SetSecurityContext` .</span><span class="sxs-lookup"><span data-stu-id="a8ee6-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="a8ee6-129">Um padrão semelhante ocorre com a conclusão de e/s.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="a8ee6-130">Se o host implementar [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), o CLR chamará `SetSecurityContext` depois que o host chamar [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="a8ee6-130">If the host implements [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="a8ee6-131">Em pontos assíncronos em threads de trabalho, as chamadas CLR `SetSecurityContext` dentro <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> ou dentro de [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), dependendo se o host ou o CLR está implementando o pool de threads.</span><span class="sxs-lookup"><span data-stu-id="a8ee6-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8ee6-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8ee6-132">Requirements</span></span>  

 <span data-ttu-id="a8ee6-133">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8ee6-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ee6-134">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a8ee6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8ee6-135">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8ee6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8ee6-136">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ee6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ee6-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="a8ee6-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="a8ee6-138">Enumeração EContextType</span><span class="sxs-lookup"><span data-stu-id="a8ee6-138">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="a8ee6-139">Interface ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a8ee6-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="a8ee6-140">Interface IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a8ee6-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="a8ee6-141">Interface IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="a8ee6-141">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="a8ee6-142">Interface IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="a8ee6-142">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="a8ee6-143">Interface IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="a8ee6-143">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
