---
title: Enumeração EMemoryAvailable
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 6a8765bfd62a2e6543661804ab8d009ce19f8813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724306"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="c12f5-102">Enumeração EMemoryAvailable</span><span class="sxs-lookup"><span data-stu-id="c12f5-102">EMemoryAvailable Enumeration</span></span>

<span data-ttu-id="c12f5-103">Contém valores que indicam a quantidade de memória física livre no computador.</span><span class="sxs-lookup"><span data-stu-id="c12f5-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="c12f5-104">Esses valores são mapeados logicamente para os eventos de memória alta e baixa retornada da `CreateMemoryResourceNotification` função na API do Windows.</span><span class="sxs-lookup"><span data-stu-id="c12f5-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12f5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c12f5-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="c12f5-106">Membros</span><span class="sxs-lookup"><span data-stu-id="c12f5-106">Members</span></span>  
  
|<span data-ttu-id="c12f5-107">Membro</span><span class="sxs-lookup"><span data-stu-id="c12f5-107">Member</span></span>|<span data-ttu-id="c12f5-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c12f5-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="c12f5-109">Há muita memória física disponível.</span><span class="sxs-lookup"><span data-stu-id="c12f5-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="c12f5-110">Há pouca memória física disponível.</span><span class="sxs-lookup"><span data-stu-id="c12f5-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="c12f5-111">A memória física disponível é neutra.</span><span class="sxs-lookup"><span data-stu-id="c12f5-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c12f5-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="c12f5-112">Remarks</span></span>  

 <span data-ttu-id="c12f5-113">Esse valor é passado pelo host para o Common Language Runtime (CLR) usando uma chamada para o método [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c12f5-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c12f5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c12f5-114">Requirements</span></span>  

 <span data-ttu-id="c12f5-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c12f5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c12f5-116">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c12f5-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c12f5-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c12f5-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c12f5-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c12f5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12f5-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="c12f5-119">See also</span></span>

- [<span data-ttu-id="c12f5-120">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="c12f5-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
