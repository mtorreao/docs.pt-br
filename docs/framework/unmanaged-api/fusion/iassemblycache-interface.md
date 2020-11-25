---
title: Interface IAssemblyCache
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
ms.openlocfilehash: df4f0ba018b55202c22cb90b22b927a9c426c4ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696850"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="fb138-102">Interface IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="fb138-102">IAssemblyCache Interface</span></span>

<span data-ttu-id="fb138-103">Representa o cache de assembly global para uso pela tecnologia Fusion.</span><span class="sxs-lookup"><span data-stu-id="fb138-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb138-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fb138-104">Methods</span></span>  
  
|<span data-ttu-id="fb138-105">Método</span><span class="sxs-lookup"><span data-stu-id="fb138-105">Method</span></span>|<span data-ttu-id="fb138-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="fb138-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb138-107">Método CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="fb138-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="fb138-108">Obtém uma referência a um novo [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fb138-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="fb138-109">Método CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="fb138-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="fb138-110">Reservado para uso interno pela tecnologia Fusion.</span><span class="sxs-lookup"><span data-stu-id="fb138-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="fb138-111">Método InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="fb138-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="fb138-112">Instala o assembly especificado no cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fb138-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="fb138-113">Método QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="fb138-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="fb138-114">Obtém os dados solicitados sobre o assembly especificado.</span><span class="sxs-lookup"><span data-stu-id="fb138-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="fb138-115">Método UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="fb138-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="fb138-116">Desinstala o assembly especificado do cache de assembly global.</span><span class="sxs-lookup"><span data-stu-id="fb138-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb138-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb138-117">Requirements</span></span>  

 <span data-ttu-id="fb138-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb138-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb138-119">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fb138-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fb138-120">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb138-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb138-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="fb138-121">See also</span></span>

- [<span data-ttu-id="fb138-122">Interfaces de fusão</span><span class="sxs-lookup"><span data-stu-id="fb138-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="fb138-123">Cache de assemblies global</span><span class="sxs-lookup"><span data-stu-id="fb138-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
