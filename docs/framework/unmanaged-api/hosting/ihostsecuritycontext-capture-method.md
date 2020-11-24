---
title: Método IHostSecurityContext::Capture
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
ms.openlocfilehash: 7760e178984798fac5cde2e8c0143a9c8716a212
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672749"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="dd9da-102">Método IHostSecurityContext::Capture</span><span class="sxs-lookup"><span data-stu-id="dd9da-102">IHostSecurityContext::Capture Method</span></span>

<span data-ttu-id="dd9da-103">Obtém um clone da instância [IHostSecurityContext](ihostsecuritycontext-interface.md) retornada de uma chamada para [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="dd9da-103">Gets a clone of the [IHostSecurityContext](ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd9da-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd9da-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd9da-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dd9da-105">Parameters</span></span>  

 `ppClonedContext`  
 <span data-ttu-id="dd9da-106">fora Um ponteiro para o endereço de um clone do `IHostSecurityContext` objeto a ser capturado.</span><span class="sxs-lookup"><span data-stu-id="dd9da-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd9da-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="dd9da-107">Return Value</span></span>  
  
|<span data-ttu-id="dd9da-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd9da-108">HRESULT</span></span>|<span data-ttu-id="dd9da-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd9da-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd9da-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd9da-110">S_OK</span></span>|<span data-ttu-id="dd9da-111">`Capture` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="dd9da-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="dd9da-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd9da-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd9da-113">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="dd9da-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd9da-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd9da-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd9da-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="dd9da-115">The call timed out.</span></span>|  
|<span data-ttu-id="dd9da-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd9da-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd9da-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="dd9da-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd9da-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd9da-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd9da-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="dd9da-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd9da-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd9da-120">E_FAIL</span></span>|<span data-ttu-id="dd9da-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="dd9da-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd9da-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="dd9da-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd9da-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd9da-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd9da-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd9da-124">Remarks</span></span>  

 <span data-ttu-id="dd9da-125">O ponteiro de interface retornado de `Capture` é um clone do contexto capturado.</span><span class="sxs-lookup"><span data-stu-id="dd9da-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="dd9da-126">Quando essas informações são movidas em um ponto de código assíncrono, seu tempo de vida é separado do ponteiro no qual a chamada foi feita.</span><span class="sxs-lookup"><span data-stu-id="dd9da-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="dd9da-127">Portanto, o ponteiro original pode ser liberado.</span><span class="sxs-lookup"><span data-stu-id="dd9da-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd9da-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd9da-128">Requirements</span></span>  

 <span data-ttu-id="dd9da-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd9da-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd9da-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dd9da-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd9da-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd9da-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd9da-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd9da-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd9da-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="dd9da-133">See also</span></span>

- [<span data-ttu-id="dd9da-134">Interface IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="dd9da-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="dd9da-135">Interface IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="dd9da-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
