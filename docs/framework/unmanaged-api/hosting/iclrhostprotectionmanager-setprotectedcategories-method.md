---
title: Método ICLRHostProtectionManager::SetProtectedCategories
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: 0557a8f1c7c495950933a44cacd23ada8e84964e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730494"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="692ca-102">Método ICLRHostProtectionManager::SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="692ca-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>

<span data-ttu-id="692ca-103">Especifica quais categorias de tipos gerenciados e membros devem ser impedidos de serem executados em código parcialmente confiável.</span><span class="sxs-lookup"><span data-stu-id="692ca-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="692ca-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="692ca-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="692ca-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="692ca-105">Parameters</span></span>  

 `categories`  
 <span data-ttu-id="692ca-106">no Uma combinação de valores [EApiCategories](eapicategories-enumeration.md) , indicando quais categorias de tipos gerenciados e membros devem ser impedidos de serem executados em código parcialmente confiável.</span><span class="sxs-lookup"><span data-stu-id="692ca-106">[in] A combination of [EApiCategories](eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="692ca-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="692ca-107">Return Value</span></span>  
  
|<span data-ttu-id="692ca-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="692ca-108">HRESULT</span></span>|<span data-ttu-id="692ca-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="692ca-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="692ca-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="692ca-110">S_OK</span></span>|<span data-ttu-id="692ca-111">`SetProtectedCategories` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="692ca-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="692ca-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="692ca-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="692ca-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="692ca-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="692ca-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="692ca-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="692ca-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="692ca-115">The call timed out.</span></span>|  
|<span data-ttu-id="692ca-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="692ca-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="692ca-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="692ca-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="692ca-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="692ca-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="692ca-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="692ca-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="692ca-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="692ca-120">E_FAIL</span></span>|<span data-ttu-id="692ca-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="692ca-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="692ca-122">Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="692ca-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="692ca-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="692ca-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="692ca-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="692ca-124">Remarks</span></span>  

 <span data-ttu-id="692ca-125">Cada `EApiCategories` valor se refere a uma lista de tipos e membros gerenciados.</span><span class="sxs-lookup"><span data-stu-id="692ca-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="692ca-126">A `EApiCategories` enumeração e o `SetProtectedCategories` método estão diretamente relacionados à classe gerenciada <xref:System.Security.Permissions.HostProtectionAttribute> , que é usada para marcar tipos gerenciados e membros que expõem recursos correspondentes às categorias descritas por `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="692ca-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="692ca-127">Para obter mais informações, consulte <xref:System.Security.Permissions.HostProtectionAttribute> e a <xref:System.Security.Permissions.HostProtectionResource> enumeração, que corresponde diretamente a `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="692ca-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="692ca-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="692ca-128">Requirements</span></span>  

 <span data-ttu-id="692ca-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="692ca-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="692ca-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="692ca-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="692ca-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="692ca-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="692ca-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="692ca-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692ca-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="692ca-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="692ca-134">Enumeração EApiCategories</span><span class="sxs-lookup"><span data-stu-id="692ca-134">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="692ca-135">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="692ca-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="692ca-136">Interface ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="692ca-136">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
