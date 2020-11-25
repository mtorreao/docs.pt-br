---
title: Método ICLRPolicyManager::SetDefaultAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: 93070690ea6b30b22949953f1ed0b8c5b1e92764
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732470"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="9f7c7-102">Método ICLRPolicyManager::SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="9f7c7-102">ICLRPolicyManager::SetDefaultAction Method</span></span>

<span data-ttu-id="9f7c7-103">Especifica a ação de política que o Common Language Runtime (CLR) deve executar quando a operação especificada ocorre.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f7c7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f7c7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f7c7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9f7c7-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="9f7c7-106">no Um dos valores de [EClrOperation](eclroperation-enumeration.md) , indicando a ação para a qual o comportamento CLR deve ser personalizado.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="9f7c7-107">no Um dos valores de [EPolicyAction](epolicyaction-enumeration.md) , indicando a ação de política que o CLR deve executar quando `operation` ocorre.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f7c7-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="9f7c7-108">Return Value</span></span>  
  
|<span data-ttu-id="9f7c7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f7c7-109">HRESULT</span></span>|<span data-ttu-id="9f7c7-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f7c7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f7c7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f7c7-111">S_OK</span></span>|<span data-ttu-id="9f7c7-112">`SetDefaultAction` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="9f7c7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f7c7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9f7c7-114">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9f7c7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9f7c7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9f7c7-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-116">The call timed out.</span></span>|  
|<span data-ttu-id="9f7c7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9f7c7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9f7c7-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9f7c7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9f7c7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9f7c7-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9f7c7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9f7c7-121">E_FAIL</span></span>|<span data-ttu-id="9f7c7-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9f7c7-123">Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9f7c7-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9f7c7-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9f7c7-125">E_INVALIDARG</span></span>|<span data-ttu-id="9f7c7-126">`action`Foi especificado um inválido para o `operation` , ou foi fornecido um valor inválido para `operation` .</span><span class="sxs-lookup"><span data-stu-id="9f7c7-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f7c7-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="9f7c7-127">Remarks</span></span>  

 <span data-ttu-id="9f7c7-128">Nem todos os valores de ação de política podem ser especificados como o comportamento padrão para operações CLR.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="9f7c7-129">`SetDefaultAction` Normalmente, pode ser usado apenas para escalonar o comportamento.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="9f7c7-130">Por exemplo, um host pode especificar que as anulações de thread sejam transformadas em anulações de thread rudes, mas não podem especificar o oposto.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="9f7c7-131">A tabela a seguir descreve os `action` valores válidos para cada `operation` valor possível.</span><span class="sxs-lookup"><span data-stu-id="9f7c7-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="9f7c7-132">Valor de `operation`</span><span class="sxs-lookup"><span data-stu-id="9f7c7-132">Value for `operation`</span></span>|<span data-ttu-id="9f7c7-133">Valores válidos para `action`</span><span class="sxs-lookup"><span data-stu-id="9f7c7-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="9f7c7-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="9f7c7-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="9f7c7-135">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="9f7c7-135">-   eAbortThread</span></span><br /><span data-ttu-id="9f7c7-136">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="9f7c7-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="9f7c7-137">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-138">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-139">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-139">-   eExitProcess</span></span><br /><span data-ttu-id="9f7c7-140">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="9f7c7-141">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9f7c7-142">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="9f7c7-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="9f7c7-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="9f7c7-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="9f7c7-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="9f7c7-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="9f7c7-145">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="9f7c7-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="9f7c7-146">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-147">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-148">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-148">-   eExitProcess</span></span><br /><span data-ttu-id="9f7c7-149">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="9f7c7-150">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9f7c7-151">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="9f7c7-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="9f7c7-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="9f7c7-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="9f7c7-153">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-154">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-155">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-155">-   eExitProcess</span></span><br /><span data-ttu-id="9f7c7-156">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="9f7c7-157">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9f7c7-158">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="9f7c7-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="9f7c7-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="9f7c7-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="9f7c7-160">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-161">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-161">-   eExitProcess</span></span><br /><span data-ttu-id="9f7c7-162">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="9f7c7-163">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9f7c7-164">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="9f7c7-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="9f7c7-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="9f7c7-165">OPR_ProcessExit</span></span>|<span data-ttu-id="9f7c7-166">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-166">-   eExitProcess</span></span><br /><span data-ttu-id="9f7c7-167">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="9f7c7-168">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9f7c7-169">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="9f7c7-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="9f7c7-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="9f7c7-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="9f7c7-171">- eNoAction</span><span class="sxs-lookup"><span data-stu-id="9f7c7-171">-   eNoAction</span></span><br /><span data-ttu-id="9f7c7-172">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="9f7c7-172">-   eAbortThread</span></span><br /><span data-ttu-id="9f7c7-173">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="9f7c7-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="9f7c7-174">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-175">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9f7c7-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="9f7c7-176">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-176">-   eExitProcess</span></span><br /><span data-ttu-id="9f7c7-177">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="9f7c7-178">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9f7c7-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9f7c7-179">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="9f7c7-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f7c7-180">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f7c7-180">Requirements</span></span>  

 <span data-ttu-id="9f7c7-181">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f7c7-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f7c7-182">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9f7c7-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f7c7-183">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f7c7-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f7c7-184">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f7c7-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f7c7-185">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f7c7-185">See also</span></span>

- [<span data-ttu-id="9f7c7-186">Enumeração EClrOperation</span><span class="sxs-lookup"><span data-stu-id="9f7c7-186">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="9f7c7-187">Enumeração EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="9f7c7-187">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="9f7c7-188">Interface ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="9f7c7-188">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
