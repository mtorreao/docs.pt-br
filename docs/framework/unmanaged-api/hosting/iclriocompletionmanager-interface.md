---
title: Interface ICLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: e23675351e1fd0de510243c9ee8b3a6dd6f29cec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714114"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="caabb-102">Interface ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="caabb-102">ICLRIoCompletionManager Interface</span></span>

<span data-ttu-id="caabb-103">Implementa um método de retorno de chamada que permite ao host notificar o Common Language Runtime (CLR) do status de solicitações de e/s especificadas.</span><span class="sxs-lookup"><span data-stu-id="caabb-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="caabb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="caabb-104">Methods</span></span>  
  
|<span data-ttu-id="caabb-105">Método</span><span class="sxs-lookup"><span data-stu-id="caabb-105">Method</span></span>|<span data-ttu-id="caabb-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="caabb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="caabb-107">Método OnComplete</span><span class="sxs-lookup"><span data-stu-id="caabb-107">OnComplete Method</span></span>](iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="caabb-108">Notifica o CLR sobre o status de uma solicitação de e/s que foi feita usando uma chamada para o método [IHostIoCompletionManager:: bind](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="caabb-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caabb-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="caabb-109">Remarks</span></span>  

 <span data-ttu-id="caabb-110">O host implementa a abstração de conclusão de e/s usando a interface [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="caabb-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="caabb-111">O CLR faz solicitações de e/s por meio dessa interface, e o host notifica o tempo de execução do resultado de tais solicitações usando a `ICLRIoCompletionManager` interface.</span><span class="sxs-lookup"><span data-stu-id="caabb-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caabb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="caabb-112">Requirements</span></span>  

 <span data-ttu-id="caabb-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caabb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caabb-114">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="caabb-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="caabb-115">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="caabb-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caabb-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caabb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caabb-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="caabb-117">See also</span></span>

- [<span data-ttu-id="caabb-118">Interface IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="caabb-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="caabb-119">Interface IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="caabb-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="caabb-120">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="caabb-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
