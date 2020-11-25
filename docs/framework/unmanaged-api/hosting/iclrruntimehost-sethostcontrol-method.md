---
title: Método ICLRRuntimeHost::SetHostControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 32483be43d4d4fe9d185c091e15a13c6feb95600
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728817"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="55d51-102">Método ICLRRuntimeHost::SetHostControl</span><span class="sxs-lookup"><span data-stu-id="55d51-102">ICLRRuntimeHost::SetHostControl Method</span></span>

<span data-ttu-id="55d51-103">Define o ponteiro de interface que o Common Language Runtime (CLR) pode usar para obter a implementação do host da [interface IHostControl](ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="55d51-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55d51-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="55d51-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55d51-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="55d51-105">Parameters</span></span>  

 `pHostControl`  
 <span data-ttu-id="55d51-106">no Um ponteiro de interface para a implementação do host da [interface IHostControl](ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="55d51-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55d51-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="55d51-107">Return Value</span></span>  
  
|<span data-ttu-id="55d51-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55d51-108">HRESULT</span></span>|<span data-ttu-id="55d51-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="55d51-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55d51-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="55d51-110">S_OK</span></span>|<span data-ttu-id="55d51-111">`SetHostControl` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="55d51-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="55d51-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55d51-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55d51-113">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="55d51-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55d51-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55d51-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55d51-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="55d51-115">The call timed out.</span></span>|  
|<span data-ttu-id="55d51-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55d51-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55d51-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="55d51-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55d51-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55d51-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55d51-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="55d51-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55d51-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55d51-120">E_FAIL</span></span>|<span data-ttu-id="55d51-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="55d51-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55d51-122">Se um método retornar E_FAIL, o CLR não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="55d51-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55d51-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="55d51-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="55d51-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="55d51-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="55d51-125">O CLR já foi inicializado.</span><span class="sxs-lookup"><span data-stu-id="55d51-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55d51-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="55d51-126">Remarks</span></span>  

 <span data-ttu-id="55d51-127">Você deve chamar `SetHostControl` antes que o CLR seja inicializado, ou seja, antes de chamar o [método Start](iclrruntimehost-start-method.md) ou usar qualquer uma das [interfaces de metadados](../metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="55d51-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="55d51-128">É recomendável que você chame `SetHostControl` imediatamente depois de chamar a [função CorBindToCurrentRuntime](corbindtocurrentruntime-function.md) ou a [função CorBindToRuntimeEx](corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="55d51-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55d51-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55d51-129">Requirements</span></span>  

 <span data-ttu-id="55d51-130">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55d51-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55d51-131">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="55d51-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55d51-132">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55d51-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55d51-133">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55d51-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d51-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="55d51-134">See also</span></span>

- [<span data-ttu-id="55d51-135">Interface ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="55d51-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="55d51-136">Interface IHostControl</span><span class="sxs-lookup"><span data-stu-id="55d51-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
