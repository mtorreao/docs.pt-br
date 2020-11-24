---
title: Método ICLRTask::RudeAbort
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: 5b0e2265810b00fe0760d4e25c0f9904a96d9f2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691039"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="56dc2-102">Método ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="56dc2-102">ICLRTask::RudeAbort Method</span></span>

<span data-ttu-id="56dc2-103">Instrui o Common Language Runtime (CLR) a anular a tarefa representada pela instância de [interface ICLRTask](iclrtask-interface.md) atual imediatamente e incondicionalmente.</span><span class="sxs-lookup"><span data-stu-id="56dc2-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56dc2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="56dc2-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="56dc2-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="56dc2-105">Return Value</span></span>  
  
|<span data-ttu-id="56dc2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56dc2-106">HRESULT</span></span>|<span data-ttu-id="56dc2-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="56dc2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56dc2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="56dc2-108">S_OK</span></span>|<span data-ttu-id="56dc2-109">`RudeAbort` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="56dc2-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="56dc2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56dc2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56dc2-111">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="56dc2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="56dc2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="56dc2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="56dc2-113">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="56dc2-113">The call timed out.</span></span>|  
|<span data-ttu-id="56dc2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="56dc2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="56dc2-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="56dc2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="56dc2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="56dc2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="56dc2-117">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="56dc2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="56dc2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56dc2-118">E_FAIL</span></span>|<span data-ttu-id="56dc2-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="56dc2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="56dc2-120">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="56dc2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="56dc2-121">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="56dc2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56dc2-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="56dc2-122">Remarks</span></span>  

 <span data-ttu-id="56dc2-123">Um host chama `RudeAbort` para anular uma tarefa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="56dc2-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="56dc2-124">Os finalizadores e as rotinas de manipulação de exceção não têm garantia de serem executadas.</span><span class="sxs-lookup"><span data-stu-id="56dc2-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56dc2-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56dc2-125">Requirements</span></span>  

 <span data-ttu-id="56dc2-126">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56dc2-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56dc2-127">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="56dc2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56dc2-128">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56dc2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56dc2-129">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56dc2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56dc2-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="56dc2-130">See also</span></span>

- [<span data-ttu-id="56dc2-131">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="56dc2-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="56dc2-132">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="56dc2-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="56dc2-133">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="56dc2-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="56dc2-134">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="56dc2-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
