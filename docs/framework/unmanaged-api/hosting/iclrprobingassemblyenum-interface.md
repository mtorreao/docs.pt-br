---
title: Interface ICLRProbingAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: 6df08889af30542af5a128cbffc38a57ce640fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728921"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="e565e-102">Interface ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="e565e-102">ICLRProbingAssemblyEnum Interface</span></span>

<span data-ttu-id="e565e-103">Fornece métodos que permitem ao host obter as identidades de investigação de um assembly usando as informações de identidade do assembly que são internas ao Common Language Runtime (CLR), sem a necessidade de criar ou compreender essa identidade.</span><span class="sxs-lookup"><span data-stu-id="e565e-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e565e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e565e-104">Methods</span></span>  
  
|<span data-ttu-id="e565e-105">Método</span><span class="sxs-lookup"><span data-stu-id="e565e-105">Method</span></span>|<span data-ttu-id="e565e-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e565e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e565e-107">Método Get</span><span class="sxs-lookup"><span data-stu-id="e565e-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="e565e-108">Obtém a identidade do assembly no índice especificado.</span><span class="sxs-lookup"><span data-stu-id="e565e-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e565e-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="e565e-109">Remarks</span></span>  

 <span data-ttu-id="e565e-110">Métodos como [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) retornam uma `ICLRProbingAssemblyEnum` instância.</span><span class="sxs-lookup"><span data-stu-id="e565e-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e565e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e565e-111">Requirements</span></span>  

 <span data-ttu-id="e565e-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e565e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e565e-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e565e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e565e-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e565e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e565e-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e565e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e565e-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="e565e-116">See also</span></span>

- [<span data-ttu-id="e565e-117">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="e565e-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e565e-118">Interface ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="e565e-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e565e-119">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="e565e-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
