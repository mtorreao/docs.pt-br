---
title: Enumeração EBindPolicyLevels
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
ms.openlocfilehash: a0992ca8ac4bfffef681c74de455a0eeb627a042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726841"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="9fbbb-102">Enumeração EBindPolicyLevels</span><span class="sxs-lookup"><span data-stu-id="9fbbb-102">EBindPolicyLevels Enumeration</span></span>

<span data-ttu-id="9fbbb-103">Fornece sinalizadores para especificar o nível no qual aplicar ou modificar a política de assembly.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fbbb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9fbbb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="9fbbb-105">Membros</span><span class="sxs-lookup"><span data-stu-id="9fbbb-105">Members</span></span>  
  
|<span data-ttu-id="9fbbb-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9fbbb-106">Member</span></span>|<span data-ttu-id="9fbbb-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9fbbb-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="9fbbb-108">Especifica que a política deve ser aplicada no nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="9fbbb-109">Especifica que a política deve ser aplicada no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="9fbbb-110">Especifica que a política deve ser aplicada no nível do host.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="9fbbb-111">Especifica nenhum sinalizador de nível de política.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="9fbbb-112">Especifica que a política deve ser aplicada no nível do Publicador.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="9fbbb-113">Especifica que a política deve ser aplicável em níveis de variável.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="9fbbb-114">Especifica que a política deve dar suporte à portabilidade entre as implementações de um assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="9fbbb-115">Consulte o [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) elemento arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-115">See the [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="9fbbb-116">Especifica que a política deve ser unificada para a do Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9fbbb-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fbbb-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="9fbbb-117">Remarks</span></span>  

 <span data-ttu-id="9fbbb-118">Essa enumeração é passada para métodos da interface [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) para especificar alterações na política de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9fbbb-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fbbb-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fbbb-119">Requirements</span></span>  

 <span data-ttu-id="9fbbb-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fbbb-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fbbb-121">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9fbbb-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fbbb-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9fbbb-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fbbb-123">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fbbb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fbbb-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="9fbbb-124">See also</span></span>

- [<span data-ttu-id="9fbbb-125">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="9fbbb-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9fbbb-126">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="9fbbb-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
