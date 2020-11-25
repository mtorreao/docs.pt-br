---
title: Método IHostMemoryManager::RegisterMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: edb29378412583d7cdec804b08f8f622d642b02f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731300"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="55811-102">Método IHostMemoryManager::RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="55811-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>

<span data-ttu-id="55811-103">Registra um ponteiro para uma função de retorno de chamada que o host chama para notificar o Common Language Runtime (CLR) da carga de memória atual no computador.</span><span class="sxs-lookup"><span data-stu-id="55811-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55811-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="55811-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55811-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="55811-105">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="55811-106">no Um ponteiro de interface para uma instância de [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) que é implementada pelo CLR.</span><span class="sxs-lookup"><span data-stu-id="55811-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55811-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="55811-107">Return Value</span></span>  
  
|<span data-ttu-id="55811-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55811-108">HRESULT</span></span>|<span data-ttu-id="55811-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="55811-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55811-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="55811-110">S_OK</span></span>|<span data-ttu-id="55811-111">`RegisterMemoryNotificationCallback` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="55811-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="55811-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55811-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55811-113">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="55811-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55811-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55811-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55811-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="55811-115">The call timed out.</span></span>|  
|<span data-ttu-id="55811-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55811-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55811-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="55811-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55811-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55811-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55811-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="55811-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55811-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55811-120">E_FAIL</span></span>|<span data-ttu-id="55811-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="55811-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55811-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="55811-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55811-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="55811-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55811-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="55811-124">Remarks</span></span>  

 <span data-ttu-id="55811-125">Como a `ICLRMemoryNotificationCallback` interface define apenas um método ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)) e, como `pCallback` é um ponteiro para uma `ICLRMemoryNotificationCallback` instância fornecida pelo CLR, o registro é efetivamente para a própria função de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="55811-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="55811-126">O host é invocado `OnMemoryNotification` para relatar condições de pressão de memória, em vez de usar a função Win32 padrão `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="55811-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="55811-127">Para obter mais informações, consulte a documentação da plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="55811-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55811-128">Chamadas para `OnMemoryNotification` nunca bloquear.</span><span class="sxs-lookup"><span data-stu-id="55811-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="55811-129">Eles sempre retornam imediatamente.</span><span class="sxs-lookup"><span data-stu-id="55811-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55811-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55811-130">Requirements</span></span>  

 <span data-ttu-id="55811-131">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55811-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55811-132">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="55811-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55811-133">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55811-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55811-134">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55811-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55811-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="55811-135">See also</span></span>

- [<span data-ttu-id="55811-136">Interface ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="55811-136">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="55811-137">Interface IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="55811-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
