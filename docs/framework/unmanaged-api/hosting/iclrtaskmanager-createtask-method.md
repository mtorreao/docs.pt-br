---
title: Método ICLRTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
ms.openlocfilehash: c8d18b78cf0185271eae763892610d13f76e42ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733991"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="a0e4f-102">Método ICLRTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="a0e4f-102">ICLRTaskManager::CreateTask Method</span></span>

<span data-ttu-id="a0e4f-103">Solicitações explicitamente que o Common Language Runtime (CLR) cria uma nova tarefa.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0e4f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a0e4f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0e4f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a0e4f-105">Parameters</span></span>  

 `pTask`  
 <span data-ttu-id="a0e4f-106">fora Um ponteiro para o endereço de um [ICLRTask](iclrtask-interface.md)recém-criado, ou NULL, se a tarefa não pôde ser criada.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-106">[out] A pointer to the address of a newly created [ICLRTask](iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0e4f-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="a0e4f-107">Return Value</span></span>  
  
|<span data-ttu-id="a0e4f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0e4f-108">HRESULT</span></span>|<span data-ttu-id="a0e4f-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="a0e4f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0e4f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0e4f-110">S_OK</span></span>|<span data-ttu-id="a0e4f-111">O método foi retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="a0e4f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0e4f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0e4f-113">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0e4f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0e4f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0e4f-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-115">The call timed out.</span></span>|  
|<span data-ttu-id="a0e4f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0e4f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0e4f-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0e4f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0e4f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0e4f-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0e4f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0e4f-120">E_FAIL</span></span>|<span data-ttu-id="a0e4f-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0e4f-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0e4f-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0e4f-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a0e4f-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a0e4f-125">Não há memória suficiente disponível para alocar o recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0e4f-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="a0e4f-126">Remarks</span></span>  

 <span data-ttu-id="a0e4f-127">O CLR cria uma nova tarefa automaticamente na inicialização, quando o código do usuário cria um thread usando tipos no <xref:System.Threading> namespace ou quando o tamanho do pool de threads é aumentado.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="a0e4f-128">Ele também cria tarefas quando o código não gerenciado faz uma chamada para uma função gerenciada.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="a0e4f-129">`CreateTask` permite que o host faça uma solicitação explícita de que o CLR crie uma nova tarefa.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="a0e4f-130">Por exemplo, o host pode invocar esse método para inicializar as estruturas de dados.</span><span class="sxs-lookup"><span data-stu-id="a0e4f-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a0e4f-131">A nova tarefa é retornada em um estado suspenso e permanece suspensa até que o host chame explicitamente [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="a0e4f-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0e4f-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0e4f-132">Requirements</span></span>  

 <span data-ttu-id="a0e4f-133">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0e4f-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0e4f-134">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a0e4f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0e4f-135">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0e4f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0e4f-136">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0e4f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0e4f-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="a0e4f-137">See also</span></span>

- [<span data-ttu-id="a0e4f-138">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="a0e4f-138">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="a0e4f-139">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a0e4f-139">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a0e4f-140">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="a0e4f-140">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a0e4f-141">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a0e4f-141">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
