---
title: Método IHostAutoEvent::Set
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
ms.openlocfilehash: facfbb85645f444b010cb1fe1c34bbe94011ac50
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680818"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="9477a-102">Método IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="9477a-102">IHostAutoEvent::Set Method</span></span>

<span data-ttu-id="9477a-103">Define a instância de [IHostAutoEvent](ihostautoevent-interface.md) atual para um estado sinalizado.</span><span class="sxs-lookup"><span data-stu-id="9477a-103">Sets the current [IHostAutoEvent](ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9477a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9477a-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9477a-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="9477a-105">Return Value</span></span>  
  
|<span data-ttu-id="9477a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9477a-106">HRESULT</span></span>|<span data-ttu-id="9477a-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="9477a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9477a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9477a-108">S_OK</span></span>|<span data-ttu-id="9477a-109">`Set` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="9477a-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="9477a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9477a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9477a-111">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="9477a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9477a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9477a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9477a-113">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="9477a-113">The call timed out.</span></span>|  
|<span data-ttu-id="9477a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9477a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9477a-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="9477a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9477a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9477a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9477a-117">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="9477a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9477a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9477a-118">E_FAIL</span></span>|<span data-ttu-id="9477a-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="9477a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9477a-120">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="9477a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9477a-121">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9477a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9477a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9477a-122">Requirements</span></span>  

 <span data-ttu-id="9477a-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9477a-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9477a-124">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9477a-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9477a-125">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9477a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9477a-126">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9477a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9477a-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="9477a-127">See also</span></span>

- [<span data-ttu-id="9477a-128">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9477a-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="9477a-129">Interface IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="9477a-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="9477a-130">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="9477a-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="9477a-131">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9477a-131">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
