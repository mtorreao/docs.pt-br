---
title: Método ICLRRuntimeHost::UnloadAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: cc5d0d65d213d952c0897a72d8ec38ea6b8b22db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700659"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="87941-102">Método ICLRRuntimeHost::UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="87941-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>

<span data-ttu-id="87941-103">Descarrega o gerenciado <xref:System.AppDomain> que corresponde ao identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="87941-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87941-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="87941-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87941-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="87941-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="87941-106">no O identificador numérico do domínio do aplicativo a ser descarregado.</span><span class="sxs-lookup"><span data-stu-id="87941-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="87941-107">[in] `true` para indicar que o Common Language Runtime (CLR) deve aguardar até concluir a execução do thread atual do aplicativo antes de tentar descarregar o domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="87941-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87941-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="87941-108">Return Value</span></span>  
  
|<span data-ttu-id="87941-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87941-109">HRESULT</span></span>|<span data-ttu-id="87941-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="87941-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87941-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="87941-111">S_OK</span></span>|<span data-ttu-id="87941-112">`UnloadAppDomain` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="87941-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="87941-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87941-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87941-114">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="87941-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87941-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87941-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87941-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="87941-116">The call timed out.</span></span>|  
|<span data-ttu-id="87941-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87941-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87941-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="87941-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87941-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87941-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87941-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="87941-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87941-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87941-121">E_FAIL</span></span>|<span data-ttu-id="87941-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="87941-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87941-123">Se um método retornar E_FAIL, o CLR não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="87941-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87941-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="87941-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87941-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="87941-125">Remarks</span></span>  

 <span data-ttu-id="87941-126">Você pode obter o identificador numérico do domínio do aplicativo no qual o thread atual está sendo executado chamando [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="87941-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="87941-127">Esse identificador corresponde à <xref:System.AppDomain.Id%2A> Propriedade do <xref:System.AppDomain> tipo gerenciado.</span><span class="sxs-lookup"><span data-stu-id="87941-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87941-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87941-128">Requirements</span></span>  

 <span data-ttu-id="87941-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87941-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87941-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="87941-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87941-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87941-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87941-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87941-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87941-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="87941-133">See also</span></span>

- [<span data-ttu-id="87941-134">Interface ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="87941-134">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
