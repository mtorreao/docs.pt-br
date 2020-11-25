---
title: Método IHostCrst::Leave
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
ms.openlocfilehash: 0752afb42b8c512450b047a5e2e7e1ff34533487
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729571"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="04281-102">Método IHostCrst::Leave</span><span class="sxs-lookup"><span data-stu-id="04281-102">IHostCrst::Leave Method</span></span>

<span data-ttu-id="04281-103">Deixa a seção crítica representada pela instância atual do [IHostCrst](ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="04281-103">Leaves the critical section that is represented by the current instance of [IHostCrst](ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04281-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="04281-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="04281-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="04281-105">Return Value</span></span>  
  
|<span data-ttu-id="04281-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04281-106">HRESULT</span></span>|<span data-ttu-id="04281-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="04281-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04281-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="04281-108">S_OK</span></span>|<span data-ttu-id="04281-109">`Leave` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="04281-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="04281-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04281-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04281-111">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="04281-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04281-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04281-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04281-113">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="04281-113">The call timed out.</span></span>|  
|<span data-ttu-id="04281-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04281-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04281-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="04281-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04281-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04281-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04281-117">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="04281-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04281-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04281-118">E_FAIL</span></span>|<span data-ttu-id="04281-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="04281-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04281-120">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="04281-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04281-121">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="04281-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04281-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="04281-122">Remarks</span></span>  

 <span data-ttu-id="04281-123">`Leave` permite que o CLR se comunique diretamente com a implementação de Threading do host, em vez de usar a `LeaveCriticalSection` função Win32 correspondente.</span><span class="sxs-lookup"><span data-stu-id="04281-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="04281-124">Um thread que assume a propriedade da seção crítica representada pela instância atual `IHostCrst` deve chamar `Leave` uma vez para cada vez que entrar nessa seção crítica.</span><span class="sxs-lookup"><span data-stu-id="04281-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04281-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04281-125">Requirements</span></span>  

 <span data-ttu-id="04281-126">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04281-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04281-127">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04281-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04281-128">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04281-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04281-129">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04281-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04281-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="04281-130">See also</span></span>

- [<span data-ttu-id="04281-131">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="04281-131">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="04281-132">Interface IHostCrst</span><span class="sxs-lookup"><span data-stu-id="04281-132">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="04281-133">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="04281-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
