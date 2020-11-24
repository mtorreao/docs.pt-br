---
title: Método IHostTaskManager::LeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
ms.openlocfilehash: 855f8a5d3582bbad59301a344d8a51198c40a051
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673040"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="73cb8-102">Método IHostTaskManager::LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="73cb8-102">IHostTaskManager::LeaveRuntime Method</span></span>

<span data-ttu-id="73cb8-103">Notifica o host de que a tarefa em execução no momento está prestes a sair do Common Language Runtime (CLR) e inserir código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="73cb8-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="73cb8-104">Uma chamada correspondente para [IHostTaskManager:: EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifica o host que a tarefa em execução no momento está reinserindo o código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="73cb8-104">A corresponding call to [IHostTaskManager::EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73cb8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="73cb8-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73cb8-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="73cb8-106">Parameters</span></span>  

 `target`  
 <span data-ttu-id="73cb8-107">no O endereço dentro do arquivo executável portátil mapeado da função não gerenciada a ser chamada.</span><span class="sxs-lookup"><span data-stu-id="73cb8-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73cb8-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="73cb8-108">Return Value</span></span>  
  
|<span data-ttu-id="73cb8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73cb8-109">HRESULT</span></span>|<span data-ttu-id="73cb8-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="73cb8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73cb8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="73cb8-111">S_OK</span></span>|<span data-ttu-id="73cb8-112">`LeaveRuntime` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="73cb8-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="73cb8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73cb8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73cb8-114">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="73cb8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73cb8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73cb8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73cb8-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="73cb8-116">The call timed out.</span></span>|  
|<span data-ttu-id="73cb8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73cb8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73cb8-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="73cb8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73cb8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73cb8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73cb8-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="73cb8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73cb8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73cb8-121">E_FAIL</span></span>|<span data-ttu-id="73cb8-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="73cb8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73cb8-123">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="73cb8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73cb8-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="73cb8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="73cb8-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="73cb8-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="73cb8-126">Não há memória suficiente disponível para concluir a alocação solicitada.</span><span class="sxs-lookup"><span data-stu-id="73cb8-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73cb8-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="73cb8-127">Remarks</span></span>  

 <span data-ttu-id="73cb8-128">Seqüências de chamadas de e para código não gerenciado podem ser aninhadas.</span><span class="sxs-lookup"><span data-stu-id="73cb8-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="73cb8-129">Por exemplo, a lista a seguir descreve uma situação hipotética na qual a sequência de chamadas para `LeaveRuntime` , [IHostTaskManager:: ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)e `IHostTaskManager::EnterRuntime` permite que o host identifique as camadas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="73cb8-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="73cb8-130">Ação</span><span class="sxs-lookup"><span data-stu-id="73cb8-130">Action</span></span>|<span data-ttu-id="73cb8-131">Chamada de método correspondente</span><span class="sxs-lookup"><span data-stu-id="73cb8-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="73cb8-132">Um executável gerenciado Visual Basic chama uma função não gerenciada escrita em C usando a invocação de plataforma.</span><span class="sxs-lookup"><span data-stu-id="73cb8-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="73cb8-133">A função C não gerenciada chama um método em uma DLL gerenciada escrita em C#.</span><span class="sxs-lookup"><span data-stu-id="73cb8-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="73cb8-134">A função C# gerenciada chama outra função não gerenciada escrita em C, também usando a invocação de plataforma.</span><span class="sxs-lookup"><span data-stu-id="73cb8-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="73cb8-135">A segunda função não gerenciada retorna a execução para a função C#.</span><span class="sxs-lookup"><span data-stu-id="73cb8-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="73cb8-136">A função C# retorna a execução para a primeira função não gerenciada.</span><span class="sxs-lookup"><span data-stu-id="73cb8-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="73cb8-137">A primeira função não gerenciada retorna a execução para o programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="73cb8-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="73cb8-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73cb8-138">Requirements</span></span>  

 <span data-ttu-id="73cb8-139">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73cb8-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73cb8-140">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="73cb8-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73cb8-141">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73cb8-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73cb8-142">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73cb8-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73cb8-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="73cb8-143">See also</span></span>

- [<span data-ttu-id="73cb8-144">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="73cb8-144">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="73cb8-145">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="73cb8-145">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="73cb8-146">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="73cb8-146">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="73cb8-147">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="73cb8-147">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
