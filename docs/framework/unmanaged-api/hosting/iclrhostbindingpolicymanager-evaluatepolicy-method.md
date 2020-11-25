---
title: Método ICLRHostBindingPolicyManager::EvaluatePolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
ms.openlocfilehash: 9840217abdf8b3e1d0917b7447572b6860c181c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720302"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="a9fb1-102">Método ICLRHostBindingPolicyManager::EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="a9fb1-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>

<span data-ttu-id="a9fb1-103">Avalia a política de associação em nome do host.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9fb1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a9fb1-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9fb1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a9fb1-105">Parameters</span></span>  

 `pwzReferenceIdentity`  
 <span data-ttu-id="a9fb1-106">no Uma referência ao assembly antes da avaliação da política.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="a9fb1-107">no Um ponteiro para um buffer que contém os dados da política.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="a9fb1-108">no O tamanho do `pbApplicationPolicy` buffer.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="a9fb1-109">fora Uma referência ao assembly após a avaliação dos novos dados de política.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="a9fb1-110">[entrada, saída] Um ponteiro para o tamanho do buffer de referência de identidade do assembly após a avaliação dos novos dados de política.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="a9fb1-111">fora Um ponteiro para uma combinação lógica ou de valores [EBindPolicyLevels](ebindpolicylevels-enumeration.md) , indicando quais políticas foram aplicadas.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9fb1-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="a9fb1-112">Return Value</span></span>  
  
|<span data-ttu-id="a9fb1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9fb1-113">HRESULT</span></span>|<span data-ttu-id="a9fb1-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="a9fb1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9fb1-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9fb1-115">S_OK</span></span>|<span data-ttu-id="a9fb1-116">A avaliação foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="a9fb1-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a9fb1-117">E_INVALIDARG</span></span>|<span data-ttu-id="a9fb1-118">`pwzReferenceIdentity`Ou `pbApplicationPolicy` é uma referência nula.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="a9fb1-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a9fb1-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a9fb1-120">`cbAppPolicySize` é pequeno demais.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="a9fb1-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9fb1-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9fb1-122">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9fb1-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9fb1-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9fb1-124">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-124">The call timed out.</span></span>|  
|<span data-ttu-id="a9fb1-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9fb1-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9fb1-126">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9fb1-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9fb1-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9fb1-128">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9fb1-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9fb1-129">E_FAIL</span></span>|<span data-ttu-id="a9fb1-130">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9fb1-131">Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9fb1-132">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9fb1-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="a9fb1-133">Remarks</span></span>  

 <span data-ttu-id="a9fb1-134">O `EvaluatePolicy` método permite que o host influencie a diretiva de associação para manter os requisitos de controle de versão de assembly específicos do host.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="a9fb1-135">O próprio mecanismo de política permanece dentro do CLR.</span><span class="sxs-lookup"><span data-stu-id="a9fb1-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9fb1-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9fb1-136">Requirements</span></span>  

 <span data-ttu-id="a9fb1-137">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9fb1-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9fb1-138">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a9fb1-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9fb1-139">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9fb1-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9fb1-140">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9fb1-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fb1-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="a9fb1-141">See also</span></span>

- [<span data-ttu-id="a9fb1-142">Interface ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a9fb1-142">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
