---
title: Interface IGCHost
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
ms.openlocfilehash: 8965797321e68443c01d05f97d147f2320a76739
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724286"
---
# <a name="igchost-interface"></a><span data-ttu-id="2c9ee-102">Interface IGCHost</span><span class="sxs-lookup"><span data-stu-id="2c9ee-102">IGCHost Interface</span></span>

<span data-ttu-id="2c9ee-103">Fornece métodos para obter informações sobre o sistema de coleta de lixo e para controlar alguns aspectos da coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="2c9ee-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c9ee-104">Começando com o .NET Framework 4,5, você pode usar o método [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) para definir o tamanho de um segmento de coleta de lixo e o tamanho máximo da geração 0 do sistema de coleta de lixo para valores maiores que o `DWORD` limite imposto pelo método [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2c9ee-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c9ee-105">Essa interface é apenas para uso de especialistas.</span><span class="sxs-lookup"><span data-stu-id="2c9ee-105">This interface is for expert usage only.</span></span> <span data-ttu-id="2c9ee-106">Ele pode afetar o desempenho de um aplicativo se for usado de forma inadequada.</span><span class="sxs-lookup"><span data-stu-id="2c9ee-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c9ee-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="2c9ee-107">Methods</span></span>  
  
|<span data-ttu-id="2c9ee-108">Método</span><span class="sxs-lookup"><span data-stu-id="2c9ee-108">Method</span></span>|<span data-ttu-id="2c9ee-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2c9ee-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c9ee-110">Método Collect</span><span class="sxs-lookup"><span data-stu-id="2c9ee-110">Collect Method</span></span>](igchost-collect-method.md)|<span data-ttu-id="2c9ee-111">Força a ocorrência de uma coleção para a geração determinada, independentemente do estado da coleta de lixo atual.</span><span class="sxs-lookup"><span data-stu-id="2c9ee-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="2c9ee-112">Método GetStats</span><span class="sxs-lookup"><span data-stu-id="2c9ee-112">GetStats Method</span></span>](igchost-getstats-method.md)|<span data-ttu-id="2c9ee-113">Obtém as estatísticas do estado atual do sistema de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="2c9ee-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="2c9ee-114">Método GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="2c9ee-114">GetThreadStats Method</span></span>](igchost-getthreadstats-method.md)|<span data-ttu-id="2c9ee-115">Obtém as estatísticas por thread para a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="2c9ee-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="2c9ee-116">Método SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="2c9ee-116">SetGCStartupLimits Method</span></span>](igchost-setgcstartuplimits-method.md)|<span data-ttu-id="2c9ee-117">Define o tamanho do segmento e o tamanho máximo para a geração 0.</span><span class="sxs-lookup"><span data-stu-id="2c9ee-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="2c9ee-118">Método SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="2c9ee-118">SetVirtualMemLimit Method</span></span>](igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="2c9ee-119">Define o tamanho máximo da memória virtual do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="2c9ee-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c9ee-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c9ee-120">Requirements</span></span>  

 <span data-ttu-id="2c9ee-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c9ee-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c9ee-122">**Cabeçalho:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="2c9ee-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="2c9ee-123">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c9ee-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c9ee-124">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c9ee-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9ee-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c9ee-125">See also</span></span>

- [<span data-ttu-id="2c9ee-126">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="2c9ee-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="2c9ee-127">Coclass CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2c9ee-127">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
