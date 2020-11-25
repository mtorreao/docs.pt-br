---
title: Interface ICLRHostBindingPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 49d1ee4dd0965d4ae5b54b53208809cfbdf7e718
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725619"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="26408-102">Interface ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="26408-102">ICLRHostBindingPolicyManager Interface</span></span>

<span data-ttu-id="26408-103">Fornece métodos para o host avaliar a política de associação atual e comunicar as alterações de política para um assembly especificado.</span><span class="sxs-lookup"><span data-stu-id="26408-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26408-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="26408-104">Methods</span></span>  
  
|<span data-ttu-id="26408-105">Método</span><span class="sxs-lookup"><span data-stu-id="26408-105">Method</span></span>|<span data-ttu-id="26408-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="26408-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26408-107">Método EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="26408-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="26408-108">Avalia a política de associação em nome do host.</span><span class="sxs-lookup"><span data-stu-id="26408-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="26408-109">Método ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="26408-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="26408-110">Modifica a política de associação para o assembly especificado e cria uma nova versão da política.</span><span class="sxs-lookup"><span data-stu-id="26408-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26408-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26408-111">Requirements</span></span>  

 <span data-ttu-id="26408-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26408-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26408-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="26408-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26408-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26408-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26408-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26408-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26408-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="26408-116">See also</span></span>

- [<span data-ttu-id="26408-117">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="26408-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="26408-118">Interface IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="26408-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="26408-119">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="26408-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
