---
title: Método ICLRHostBindingPolicyManager::ModifyApplicationPolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
ms.openlocfilehash: 8da9c9fea5cf5b3a27eeb9d0222f0845c832b7da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714192"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="857b4-102">Método ICLRHostBindingPolicyManager::ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="857b4-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>

<span data-ttu-id="857b4-103">Modifica a política de associação para o assembly especificado e cria uma nova versão da política.</span><span class="sxs-lookup"><span data-stu-id="857b4-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857b4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="857b4-104">Syntax</span></span>  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="857b4-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="857b4-105">Parameters</span></span>  

 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="857b4-106">no A identidade do assembly a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="857b4-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="857b4-107">no A nova identidade do assembly modificado.</span><span class="sxs-lookup"><span data-stu-id="857b4-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="857b4-108">no Um ponteiro para um buffer que contém os dados da política de associação para o assembly modificar.</span><span class="sxs-lookup"><span data-stu-id="857b4-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="857b4-109">no O tamanho da política de associação a ser substituída.</span><span class="sxs-lookup"><span data-stu-id="857b4-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="857b4-110">no Uma combinação lógica ou de valores [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) , indicando o controle do redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="857b4-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="857b4-111">fora Um ponteiro para um buffer que contém os novos dados de diretiva de associação.</span><span class="sxs-lookup"><span data-stu-id="857b4-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="857b4-112">[entrada, saída] Um ponteiro para o tamanho do novo buffer de diretiva de associação.</span><span class="sxs-lookup"><span data-stu-id="857b4-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="857b4-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="857b4-113">Return Value</span></span>  
  
|<span data-ttu-id="857b4-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="857b4-114">HRESULT</span></span>|<span data-ttu-id="857b4-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="857b4-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="857b4-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="857b4-116">S_OK</span></span>|<span data-ttu-id="857b4-117">A política foi modificada com êxito.</span><span class="sxs-lookup"><span data-stu-id="857b4-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="857b4-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="857b4-118">E_INVALIDARG</span></span>|<span data-ttu-id="857b4-119">`pwzSourceAssemblyIdentity` ou `pwzTargetAssemblyIdentity` era uma referência nula.</span><span class="sxs-lookup"><span data-stu-id="857b4-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="857b4-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="857b4-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="857b4-121">`pbNewApplicationPolicy` é pequeno demais.</span><span class="sxs-lookup"><span data-stu-id="857b4-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="857b4-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="857b4-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="857b4-123">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="857b4-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="857b4-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="857b4-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="857b4-125">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="857b4-125">The call timed out.</span></span>|  
|<span data-ttu-id="857b4-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="857b4-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="857b4-127">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="857b4-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="857b4-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="857b4-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="857b4-129">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="857b4-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="857b4-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="857b4-130">E_FAIL</span></span>|<span data-ttu-id="857b4-131">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="857b4-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="857b4-132">Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="857b4-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="857b4-133">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="857b4-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="857b4-134">Comentários</span><span class="sxs-lookup"><span data-stu-id="857b4-134">Remarks</span></span>  

 <span data-ttu-id="857b4-135">O `ModifyApplicationPolicy` método pode ser chamado duas vezes.</span><span class="sxs-lookup"><span data-stu-id="857b4-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="857b4-136">A primeira chamada deve fornecer um valor nulo para o `pbNewApplicationPolicy` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="857b4-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="857b4-137">Essa chamada retornará com o valor necessário para `pcbNewAppPolicySize` .</span><span class="sxs-lookup"><span data-stu-id="857b4-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="857b4-138">A segunda chamada deve fornecer esse valor para `pcbNewAppPolicySize` e apontar para um buffer desse tamanho para `pbNewApplicationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="857b4-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="857b4-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="857b4-139">Requirements</span></span>  

 <span data-ttu-id="857b4-140">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="857b4-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="857b4-141">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="857b4-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="857b4-142">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="857b4-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="857b4-143">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="857b4-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857b4-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="857b4-144">See also</span></span>

- [<span data-ttu-id="857b4-145">Interface ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="857b4-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
