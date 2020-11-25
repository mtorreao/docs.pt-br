---
title: Estrutura COR_GC_THREAD_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 25a90965dc5466b7cf1a07140705424cf2ba4cd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699229"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="7fb47-102">Estrutura COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="7fb47-102">COR_GC_THREAD_STATS Structure</span></span>

<span data-ttu-id="7fb47-103">Contém estatísticas por thread referentes à coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="7fb47-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fb47-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7fb47-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="7fb47-105">Membros</span><span class="sxs-lookup"><span data-stu-id="7fb47-105">Members</span></span>  
  
|<span data-ttu-id="7fb47-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7fb47-106">Member</span></span>|<span data-ttu-id="7fb47-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7fb47-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="7fb47-108">O número de bytes de memória alocados no thread que está associado à instância atual `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="7fb47-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="7fb47-109">Esse número é limpo para zero sempre que uma coleta de lixo de geração zero ocorre.</span><span class="sxs-lookup"><span data-stu-id="7fb47-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="7fb47-110">O número de bytes promovidos para uma geração mais alta na coleta de lixo mais recente.</span><span class="sxs-lookup"><span data-stu-id="7fb47-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fb47-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="7fb47-111">Remarks</span></span>  

 <span data-ttu-id="7fb47-112">[ICLRTask:: GetMemStats](iclrtask-getmemstats-method.md) usa um parâmetro de saída do tipo `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="7fb47-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fb47-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fb47-113">Requirements</span></span>  

 <span data-ttu-id="7fb47-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fb47-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fb47-115">**Cabeçalho:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="7fb47-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="7fb47-116">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7fb47-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fb47-117">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fb47-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb47-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="7fb47-118">See also</span></span>

- [<span data-ttu-id="7fb47-119">Estruturas de hospedagem</span><span class="sxs-lookup"><span data-stu-id="7fb47-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="7fb47-120">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="7fb47-120">IHostTask Interface</span></span>](ihosttask-interface.md)
