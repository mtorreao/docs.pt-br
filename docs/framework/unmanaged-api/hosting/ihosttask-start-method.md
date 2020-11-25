---
title: Método IHostTask::Start
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: 4143c3d25dd5262a10b53708a249910cc79f5314
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720432"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="71abf-102">Método IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="71abf-102">IHostTask::Start Method</span></span>

<span data-ttu-id="71abf-103">Solicita que o host mova a tarefa representada pela instância [IHostTask](ihosttask-interface.md) atual de uma suspensa para um estado ativo, na qual o código pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="71abf-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71abf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="71abf-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="71abf-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="71abf-105">Return Value</span></span>  
  
|<span data-ttu-id="71abf-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71abf-106">HRESULT</span></span>|<span data-ttu-id="71abf-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="71abf-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71abf-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="71abf-108">S_OK</span></span>|<span data-ttu-id="71abf-109">Início retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="71abf-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="71abf-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71abf-110">E_FAIL</span></span>|<span data-ttu-id="71abf-111">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="71abf-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71abf-112">Quando um método retorna E_FAIL, o Common Language Runtime (CLR) não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="71abf-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="71abf-113">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71abf-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71abf-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="71abf-114">Remarks</span></span>  

 <span data-ttu-id="71abf-115">`Start` sempre retorna um valor HRESULT de S_OK, exceto nos casos em que ocorreu uma falha catastrófica.</span><span class="sxs-lookup"><span data-stu-id="71abf-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71abf-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71abf-116">Requirements</span></span>  

 <span data-ttu-id="71abf-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71abf-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71abf-118">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71abf-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71abf-119">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71abf-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71abf-120">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71abf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71abf-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="71abf-121">See also</span></span>

- [<span data-ttu-id="71abf-122">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="71abf-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="71abf-123">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="71abf-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="71abf-124">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="71abf-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="71abf-125">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="71abf-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
