---
title: Método ICLRPolicyManager::SetActionOnTimeout
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: 3ddd78ea35d5709abb30af085b2212a09b28c2ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725554"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="27c70-102">Método ICLRPolicyManager::SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="27c70-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>

<span data-ttu-id="27c70-103">Especifica a ação de política que o Common Language Runtime (CLR) deve executar quando a operação especificada atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="27c70-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c70-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="27c70-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27c70-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="27c70-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="27c70-106">no Um dos valores de [EClrOperation](eclroperation-enumeration.md) , que indica a operação para a qual especificar a ação de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="27c70-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="27c70-107">Os seguintes valores têm suporte:</span><span class="sxs-lookup"><span data-stu-id="27c70-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="27c70-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="27c70-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="27c70-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="27c70-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="27c70-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="27c70-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="27c70-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="27c70-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="27c70-112">no Um dos valores de [EPolicyAction](epolicyaction-enumeration.md) , indicando a ação da política a ser executada quando a operação atingir o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="27c70-112">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27c70-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="27c70-113">Return Value</span></span>  
  
|<span data-ttu-id="27c70-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27c70-114">HRESULT</span></span>|<span data-ttu-id="27c70-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="27c70-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27c70-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="27c70-116">S_OK</span></span>|<span data-ttu-id="27c70-117">`SetActionOnTimeout` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="27c70-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="27c70-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27c70-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27c70-119">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="27c70-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27c70-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27c70-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27c70-121">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="27c70-121">The call timed out.</span></span>|  
|<span data-ttu-id="27c70-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27c70-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27c70-123">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="27c70-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27c70-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27c70-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27c70-125">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="27c70-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27c70-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27c70-126">E_FAIL</span></span>|<span data-ttu-id="27c70-127">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="27c70-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27c70-128">Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="27c70-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27c70-129">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="27c70-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="27c70-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="27c70-130">E_INVALIDARG</span></span>|<span data-ttu-id="27c70-131">Não é possível definir um tempo limite para o especificado `operation` ou um valor inválido foi fornecido para `operation` .</span><span class="sxs-lookup"><span data-stu-id="27c70-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27c70-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="27c70-132">Remarks</span></span>  

 <span data-ttu-id="27c70-133">O valor de tempo limite pode ser o tempo limite padrão definido pelo CLR ou um valor especificado pelo host em uma chamada para o método [ICLRPolicyManager:: SetTimeout](iclrpolicymanager-settimeout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="27c70-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="27c70-134">Nem todos os valores de ação de política podem ser especificados como o comportamento de tempo limite para operações de CLR.</span><span class="sxs-lookup"><span data-stu-id="27c70-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="27c70-135">`SetActionOnTimeout` normalmente é usado apenas para escalonar o comportamento.</span><span class="sxs-lookup"><span data-stu-id="27c70-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="27c70-136">Por exemplo, um host pode especificar que as anulações de thread sejam transformadas em anulações de thread rudes, mas não podem especificar o oposto.</span><span class="sxs-lookup"><span data-stu-id="27c70-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="27c70-137">A tabela a seguir descreve os `action` valores válidos para os `operation` valores válidos.</span><span class="sxs-lookup"><span data-stu-id="27c70-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="27c70-138">Valor de `operation`</span><span class="sxs-lookup"><span data-stu-id="27c70-138">Value for `operation`</span></span>|<span data-ttu-id="27c70-139">Valores válidos para `action`</span><span class="sxs-lookup"><span data-stu-id="27c70-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="27c70-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="27c70-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="27c70-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="27c70-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="27c70-142">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="27c70-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="27c70-143">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="27c70-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="27c70-144">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="27c70-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="27c70-145">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-145">-   eExitProcess</span></span><br /><span data-ttu-id="27c70-146">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="27c70-147">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="27c70-148">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="27c70-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="27c70-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="27c70-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="27c70-150">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="27c70-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="27c70-151">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="27c70-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="27c70-152">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-152">-   eExitProcess</span></span><br /><span data-ttu-id="27c70-153">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="27c70-154">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="27c70-155">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="27c70-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="27c70-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="27c70-156">OPR_ProcessExit</span></span>|<span data-ttu-id="27c70-157">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-157">-   eExitProcess</span></span><br /><span data-ttu-id="27c70-158">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="27c70-159">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="27c70-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="27c70-160">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="27c70-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27c70-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27c70-161">Requirements</span></span>  

 <span data-ttu-id="27c70-162">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27c70-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27c70-163">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="27c70-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27c70-164">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27c70-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27c70-165">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27c70-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c70-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="27c70-166">See also</span></span>

- [<span data-ttu-id="27c70-167">Enumeração EClrOperation</span><span class="sxs-lookup"><span data-stu-id="27c70-167">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="27c70-168">Enumeração EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="27c70-168">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="27c70-169">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="27c70-169">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="27c70-170">Interface ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="27c70-170">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
