---
title: Interface ICLRMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689531"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="d2cfc-102">Interface ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="d2cfc-102">ICLRMemoryNotificationCallback Interface</span></span>

<span data-ttu-id="d2cfc-103">Permite que o host relate condições de pressão de memória usando uma abordagem semelhante à da `CreateMemoryResourceNotification` função do Win32.</span><span class="sxs-lookup"><span data-stu-id="d2cfc-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2cfc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d2cfc-104">Methods</span></span>  
  
|<span data-ttu-id="d2cfc-105">Método</span><span class="sxs-lookup"><span data-stu-id="d2cfc-105">Method</span></span>|<span data-ttu-id="d2cfc-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d2cfc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2cfc-107">Método OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="d2cfc-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="d2cfc-108">Notifica o Common Language Runtime (CLR) da carga de memória no computador.</span><span class="sxs-lookup"><span data-stu-id="d2cfc-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2cfc-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="d2cfc-109">Remarks</span></span>  

 <span data-ttu-id="d2cfc-110">O host usa a `ICLRMemoryNotificationCallback` interface para solicitar que os recursos de memória livre do CLR.</span><span class="sxs-lookup"><span data-stu-id="d2cfc-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2cfc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2cfc-111">Requirements</span></span>  

 <span data-ttu-id="d2cfc-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2cfc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2cfc-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d2cfc-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2cfc-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2cfc-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2cfc-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2cfc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2cfc-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="d2cfc-116">See also</span></span>

- [<span data-ttu-id="d2cfc-117">Interface IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="d2cfc-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="d2cfc-118">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="d2cfc-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
