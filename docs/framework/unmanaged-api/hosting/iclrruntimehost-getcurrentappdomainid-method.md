---
title: Método ICLRRuntimeHost::GetCurrentAppDomainId
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
ms.openlocfilehash: 2b1c9e99604664c99960a0741de6eae6b38fe963
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728843"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="3bc01-102">Método ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="3bc01-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>

<span data-ttu-id="3bc01-103">Obtém o identificador numérico do <xref:System.AppDomain> que está sendo executado no momento.</span><span class="sxs-lookup"><span data-stu-id="3bc01-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bc01-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3bc01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bc01-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3bc01-105">Parameters</span></span>  

 `pdwAppDomainId`  
 <span data-ttu-id="3bc01-106">fora O identificador numérico do <xref:System.AppDomain> que está sendo executado no momento.</span><span class="sxs-lookup"><span data-stu-id="3bc01-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bc01-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="3bc01-107">Return Value</span></span>  
  
|<span data-ttu-id="3bc01-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3bc01-108">HRESULT</span></span>|<span data-ttu-id="3bc01-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="3bc01-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bc01-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bc01-110">S_OK</span></span>|<span data-ttu-id="3bc01-111">`GetCurrentAppDomainId` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="3bc01-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="3bc01-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3bc01-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3bc01-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="3bc01-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3bc01-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3bc01-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3bc01-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="3bc01-115">The call timed out.</span></span>|  
|<span data-ttu-id="3bc01-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3bc01-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3bc01-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="3bc01-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3bc01-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3bc01-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3bc01-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="3bc01-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3bc01-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3bc01-120">E_FAIL</span></span>|<span data-ttu-id="3bc01-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="3bc01-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3bc01-122">Se um método retornar E_FAIL, o CLR não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="3bc01-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3bc01-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3bc01-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bc01-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="3bc01-124">Remarks</span></span>  

 <span data-ttu-id="3bc01-125">O `pdwAppDomainId` parâmetro é definido como o valor da <xref:System.AppDomain.Id%2A> Propriedade do <xref:System.AppDomain> na qual o thread atual está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="3bc01-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bc01-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bc01-126">Requirements</span></span>  

 <span data-ttu-id="3bc01-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bc01-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bc01-128">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3bc01-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bc01-129">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3bc01-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bc01-130">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bc01-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc01-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="3bc01-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="3bc01-132">Interface ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3bc01-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
