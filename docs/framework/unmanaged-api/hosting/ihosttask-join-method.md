---
title: Método IHostTask::Join
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
ms.openlocfilehash: 37156b03b184d06e0c7b03d7d7a9a018793bbb98
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721628"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="04c4c-102">Método IHostTask::Join</span><span class="sxs-lookup"><span data-stu-id="04c4c-102">IHostTask::Join Method</span></span>

<span data-ttu-id="04c4c-103">Bloqueia a tarefa de chamada até que a tarefa representada pela instância [IHostTask](ihosttask-interface.md) atual seja concluída, o intervalo de tempo especificado decorre ou [IHostTask:: Alert](ihosttask-alert-method.md) seja chamado.</span><span class="sxs-lookup"><span data-stu-id="04c4c-103">Blocks the calling task until the task represented by the current [IHostTask](ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c4c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="04c4c-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04c4c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="04c4c-105">Parameters</span></span>  

 `milliseconds`  
 <span data-ttu-id="04c4c-106">no O intervalo de tempo, em milissegundos, para aguardar até que a tarefa seja encerrada.</span><span class="sxs-lookup"><span data-stu-id="04c4c-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="04c4c-107">Se esse intervalo expirar antes da tarefa ser encerrada, a tarefa de chamada desbloqueará.</span><span class="sxs-lookup"><span data-stu-id="04c4c-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="04c4c-108">no Um dos valores de [WAIT_OPTION](wait-option-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="04c4c-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values.</span></span> <span data-ttu-id="04c4c-109">Um valor de WAIT_ALERTABLE instrui o host a ativar a tarefa se `Alert` for chamado antes de `milliseconds` decorrer.</span><span class="sxs-lookup"><span data-stu-id="04c4c-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04c4c-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="04c4c-110">Return Value</span></span>  
  
|<span data-ttu-id="04c4c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04c4c-111">HRESULT</span></span>|<span data-ttu-id="04c4c-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="04c4c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04c4c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="04c4c-113">S_OK</span></span>|<span data-ttu-id="04c4c-114">`Join` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="04c4c-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="04c4c-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04c4c-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04c4c-116">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="04c4c-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04c4c-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04c4c-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04c4c-118">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="04c4c-118">The call timed out.</span></span>|  
|<span data-ttu-id="04c4c-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04c4c-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04c4c-120">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="04c4c-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04c4c-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04c4c-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04c4c-122">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava aguardando, ou a `IHostTask` instância atual não está associada a uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="04c4c-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="04c4c-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04c4c-123">E_FAIL</span></span>|<span data-ttu-id="04c4c-124">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="04c4c-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04c4c-125">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="04c4c-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04c4c-126">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="04c4c-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04c4c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04c4c-127">Requirements</span></span>  

 <span data-ttu-id="04c4c-128">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04c4c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04c4c-129">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04c4c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04c4c-130">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04c4c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04c4c-131">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04c4c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c4c-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="04c4c-132">See also</span></span>

- [<span data-ttu-id="04c4c-133">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="04c4c-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="04c4c-134">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="04c4c-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="04c4c-135">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="04c4c-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="04c4c-136">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="04c4c-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="04c4c-137">Enumeração WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="04c4c-137">WAIT_OPTION Enumeration</span></span>](wait-option-enumeration.md)
