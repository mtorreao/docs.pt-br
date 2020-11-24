---
title: Interface IHostAssemblyManager
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: a06e7f13b6de9450aa2a81f28f591c0a3ce8db0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680964"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="faff7-102">Interface IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="faff7-102">IHostAssemblyManager Interface</span></span>

<span data-ttu-id="faff7-103">Fornece métodos que permitem que um host especifique conjuntos de assemblies que devem ser carregados pelo Common Language Runtime (CLR) ou pelo host.</span><span class="sxs-lookup"><span data-stu-id="faff7-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="faff7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="faff7-104">Methods</span></span>  
  
|<span data-ttu-id="faff7-105">Método</span><span class="sxs-lookup"><span data-stu-id="faff7-105">Method</span></span>|<span data-ttu-id="faff7-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="faff7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="faff7-107">Método GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="faff7-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="faff7-108">Obtém um ponteiro de interface para um [IHostAssemblyStore](ihostassemblystore-interface.md) que representa a lista de assemblies carregados pelo host.</span><span class="sxs-lookup"><span data-stu-id="faff7-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="faff7-109">Método GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="faff7-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="faff7-110">Obtém um ponteiro de interface para um [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa a lista de assemblies que o host espera que o CLR carregue.</span><span class="sxs-lookup"><span data-stu-id="faff7-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faff7-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="faff7-111">Remarks</span></span>  

 <span data-ttu-id="faff7-112">Não é necessário que o host implemente `IHostAssemblyManager` ou `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="faff7-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="faff7-113">Se o host implementar `IHostAssemblyManager` , ele também deverá implementar `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="faff7-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="faff7-114">As consultas de tempo de execução para um `IHostAssemblyManager` chamando [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) na inicialização com um `IID` de IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="faff7-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faff7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="faff7-115">Requirements</span></span>  

 <span data-ttu-id="faff7-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faff7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faff7-117">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="faff7-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="faff7-118">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="faff7-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="faff7-119">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faff7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faff7-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="faff7-120">See also</span></span>

- [<span data-ttu-id="faff7-121">Interface ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="faff7-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="faff7-122">Interface IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="faff7-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="faff7-123">Interface IHostControl</span><span class="sxs-lookup"><span data-stu-id="faff7-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="faff7-124">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="faff7-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
