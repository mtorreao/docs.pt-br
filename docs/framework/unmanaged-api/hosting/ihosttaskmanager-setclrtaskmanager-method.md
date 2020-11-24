---
title: Método IHostTaskManager::SetCLRTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: 23d0679599c681468caa2507518d0ae3144ac26a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669790"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="9d822-102">Método IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9d822-102">IHostTaskManager::SetCLRTaskManager Method</span></span>

<span data-ttu-id="9d822-103">Fornece ao host um ponteiro de interface para uma instância [ICLRTaskManager](iclrtaskmanager-interface.md) implementada pelo Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9d822-103">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d822-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9d822-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d822-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9d822-105">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="9d822-106">no Um ponteiro para uma `ICLRTaskManager` instância implementada pelo Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9d822-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d822-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="9d822-107">Return Value</span></span>  
  
|<span data-ttu-id="9d822-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d822-108">HRESULT</span></span>|<span data-ttu-id="9d822-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d822-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d822-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d822-110">S_OK</span></span>|<span data-ttu-id="9d822-111">`SetCLRTaskManager` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="9d822-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="9d822-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9d822-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9d822-113">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="9d822-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9d822-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9d822-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9d822-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="9d822-115">The call timed out.</span></span>|  
|<span data-ttu-id="9d822-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d822-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9d822-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="9d822-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9d822-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9d822-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9d822-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="9d822-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9d822-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9d822-120">E_FAIL</span></span>|<span data-ttu-id="9d822-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="9d822-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9d822-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="9d822-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9d822-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9d822-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d822-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="9d822-124">Remarks</span></span>  

 <span data-ttu-id="9d822-125">O tempo de execução chama `SetCLRTaskManager` para fornecer ao host um ponteiro de interface para uma `ICLRTaskManager` instância.</span><span class="sxs-lookup"><span data-stu-id="9d822-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d822-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d822-126">Requirements</span></span>  

 <span data-ttu-id="9d822-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d822-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d822-128">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9d822-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d822-129">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d822-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d822-130">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d822-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d822-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="9d822-131">See also</span></span>

- [<span data-ttu-id="9d822-132">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="9d822-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="9d822-133">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9d822-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="9d822-134">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="9d822-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="9d822-135">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="9d822-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
