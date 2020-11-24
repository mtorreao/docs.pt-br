---
title: Método IHostSecurityManager::SetThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
ms.openlocfilehash: 5a2b2e5560c292598f0110de9445eb66ba794997
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683102"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="08fdd-102">Método IHostSecurityManager::SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="08fdd-102">IHostSecurityManager::SetThreadToken Method</span></span>

<span data-ttu-id="08fdd-103">Define um identificador para o thread em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="08fdd-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08fdd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="08fdd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08fdd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="08fdd-105">Parameters</span></span>  

 `hToken`  
 <span data-ttu-id="08fdd-106">no Um identificador para o token a ser definido para o thread em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="08fdd-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08fdd-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="08fdd-107">Return Value</span></span>  
  
|<span data-ttu-id="08fdd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08fdd-108">HRESULT</span></span>|<span data-ttu-id="08fdd-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="08fdd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08fdd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="08fdd-110">S_OK</span></span>|<span data-ttu-id="08fdd-111">`SetThreadToken` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="08fdd-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="08fdd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08fdd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08fdd-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="08fdd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08fdd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08fdd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08fdd-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="08fdd-115">The call timed out.</span></span>|  
|<span data-ttu-id="08fdd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08fdd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08fdd-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="08fdd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08fdd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08fdd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08fdd-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="08fdd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08fdd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08fdd-120">E_FAIL</span></span>|<span data-ttu-id="08fdd-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="08fdd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08fdd-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="08fdd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08fdd-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="08fdd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08fdd-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="08fdd-124">Remarks</span></span>  

 <span data-ttu-id="08fdd-125">`IHostSecurityManager::SetThreadToken` comporta-se da mesma forma que a função Win32 correspondente do mesmo nome, exceto que a função do Win32 permite que o chamador passe um identificador para um thread arbitrário, enquanto `IHostSecurityManager::SetThreadToken` pode associar um token somente com o thread em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="08fdd-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="08fdd-126">O `HANDLE` tipo não é compatível COM com; ou seja, seu tamanho é específico para um sistema operacional e requer marshaling personalizado.</span><span class="sxs-lookup"><span data-stu-id="08fdd-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="08fdd-127">Portanto, esse token é para uso apenas dentro do processo, entre o CLR e o host.</span><span class="sxs-lookup"><span data-stu-id="08fdd-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08fdd-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08fdd-128">Requirements</span></span>  

 <span data-ttu-id="08fdd-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08fdd-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08fdd-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="08fdd-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08fdd-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08fdd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08fdd-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08fdd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08fdd-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="08fdd-133">See also</span></span>

- [<span data-ttu-id="08fdd-134">Interface IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="08fdd-134">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="08fdd-135">Interface IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="08fdd-135">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
