---
title: Método ICLROnEventManager::RegisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: 7f0770585e977f5299a40517c28dfb776b2ab898
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725606"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="f83c3-102">Método ICLROnEventManager::RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="f83c3-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>

<span data-ttu-id="f83c3-103">Registra um ponteiro de retorno de chamada para o evento especificado.</span><span class="sxs-lookup"><span data-stu-id="f83c3-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83c3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f83c3-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f83c3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f83c3-105">Parameters</span></span>  

 `event`  
 <span data-ttu-id="f83c3-106">no Um dos valores de [EClrEvent](eclrevent-enumeration.md) , indicando o evento para o qual registrar o ponteiro de retorno de chamada descrito por `pAction` .</span><span class="sxs-lookup"><span data-stu-id="f83c3-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="f83c3-107">no Um ponteiro para um objeto [IActionOnCLREvent](iactiononclrevent-interface.md) que é chamado quando o evento registrado é acionado.</span><span class="sxs-lookup"><span data-stu-id="f83c3-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f83c3-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f83c3-108">Return Value</span></span>  
  
|<span data-ttu-id="f83c3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f83c3-109">HRESULT</span></span>|<span data-ttu-id="f83c3-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="f83c3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f83c3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f83c3-111">S_OK</span></span>|<span data-ttu-id="f83c3-112">`RegisterActionOnEvent` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="f83c3-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f83c3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f83c3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f83c3-114">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="f83c3-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f83c3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f83c3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f83c3-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="f83c3-116">The call timed out.</span></span>|  
|<span data-ttu-id="f83c3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f83c3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f83c3-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="f83c3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f83c3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f83c3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f83c3-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="f83c3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f83c3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f83c3-121">E_FAIL</span></span>|<span data-ttu-id="f83c3-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="f83c3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f83c3-123">Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="f83c3-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f83c3-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f83c3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f83c3-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="f83c3-125">Remarks</span></span>  

 <span data-ttu-id="f83c3-126">O host pode registrar retornos de chamada para um ou ambos os dois tipos de evento descritos por `EClrEvent` .</span><span class="sxs-lookup"><span data-stu-id="f83c3-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="f83c3-127">O host obtém a `ICLROnEventManager` interface chamando o método [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f83c3-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f83c3-128">Os eventos que o `RegisterActionOnEvent` registro podem ser acionados mais de uma vez e de threads diferentes para sinalizar um descarregamento ou desabilitar o CLR.</span><span class="sxs-lookup"><span data-stu-id="f83c3-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f83c3-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f83c3-129">Requirements</span></span>  

 <span data-ttu-id="f83c3-130">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f83c3-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f83c3-131">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f83c3-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f83c3-132">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f83c3-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f83c3-133">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f83c3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83c3-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="f83c3-134">See also</span></span>

- [<span data-ttu-id="f83c3-135">Enumeração EClrEvent</span><span class="sxs-lookup"><span data-stu-id="f83c3-135">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="f83c3-136">Interface IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="f83c3-136">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="f83c3-137">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f83c3-137">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f83c3-138">Interface ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="f83c3-138">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
