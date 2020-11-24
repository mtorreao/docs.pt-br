---
title: Interface IHostManualEvent
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 50e37b770e3ee6e0a5cdfca61fc5b09749e5735f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673174"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="409ce-102">Interface IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="409ce-102">IHostManualEvent Interface</span></span>

<span data-ttu-id="409ce-103">Fornece a implementação do host de uma representação de um evento de redefinição manual.</span><span class="sxs-lookup"><span data-stu-id="409ce-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="409ce-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="409ce-104">Methods</span></span>  
  
|<span data-ttu-id="409ce-105">Método</span><span class="sxs-lookup"><span data-stu-id="409ce-105">Method</span></span>|<span data-ttu-id="409ce-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="409ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="409ce-107">Método Reset</span><span class="sxs-lookup"><span data-stu-id="409ce-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="409ce-108">Redefine a `IHostManualEvent` instância atual para um estado não sinalizado.</span><span class="sxs-lookup"><span data-stu-id="409ce-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="409ce-109">Método Set</span><span class="sxs-lookup"><span data-stu-id="409ce-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="409ce-110">Define a `IHostManualEvent` instância atual para um estado sinalizado.</span><span class="sxs-lookup"><span data-stu-id="409ce-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="409ce-111">Método Wait</span><span class="sxs-lookup"><span data-stu-id="409ce-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="409ce-112">Faz com que a `IHostManualEvent` instância atual aguarde até que ela seja propriedade ou uma quantidade especificada de tempo decorre.</span><span class="sxs-lookup"><span data-stu-id="409ce-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="409ce-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="409ce-113">Requirements</span></span>  

 <span data-ttu-id="409ce-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="409ce-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="409ce-115">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="409ce-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="409ce-116">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="409ce-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="409ce-117">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="409ce-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="409ce-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="409ce-118">See also</span></span>

- [<span data-ttu-id="409ce-119">Interface ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="409ce-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="409ce-120">Interface IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="409ce-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="409ce-121">Interface IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="409ce-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="409ce-122">Interface IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="409ce-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="409ce-123">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="409ce-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
