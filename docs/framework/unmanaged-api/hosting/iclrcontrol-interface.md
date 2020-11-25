---
title: Interface ICLRControl
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: acf449014f5bf5683d5488f8ed2ead963676fe6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728323"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="eb897-102">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="eb897-102">ICLRControl Interface</span></span>

<span data-ttu-id="eb897-103">Fornece métodos que permitem que um host obtenha referências e configure aspectos do, o Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="eb897-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb897-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="eb897-104">Methods</span></span>  
  
|<span data-ttu-id="eb897-105">Método</span><span class="sxs-lookup"><span data-stu-id="eb897-105">Method</span></span>|<span data-ttu-id="eb897-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="eb897-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb897-107">Método GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="eb897-107">GetCLRManager Method</span></span>](iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="eb897-108">Obtém um ponteiro de interface para uma instância de qualquer um dos tipos de Gerenciador que o host pode usar para configurar o CLR.</span><span class="sxs-lookup"><span data-stu-id="eb897-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="eb897-109">Método SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="eb897-109">SetAppDomainManagerType Method</span></span>](iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="eb897-110">Define um tipo derivado de <xref:System.AppDomainManager> como o tipo para gerenciadores de domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="eb897-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb897-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb897-111">Requirements</span></span>  

 <span data-ttu-id="eb897-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb897-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb897-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eb897-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb897-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb897-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb897-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb897-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb897-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="eb897-116">See also</span></span>

- [<span data-ttu-id="eb897-117">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="eb897-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="eb897-118">Interface ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="eb897-118">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="eb897-119">Interface ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="eb897-119">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="eb897-120">Interface ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="eb897-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="eb897-121">Interface ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="eb897-121">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="eb897-122">Interface ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="eb897-122">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="eb897-123">Interface ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="eb897-123">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="eb897-124">Interface IHostControl</span><span class="sxs-lookup"><span data-stu-id="eb897-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="eb897-125">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="eb897-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
