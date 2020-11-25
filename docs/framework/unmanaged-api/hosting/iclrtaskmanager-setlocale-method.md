---
title: Método ICLRTaskManager::SetLocale
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
ms.openlocfilehash: 5f799c140705a5279c996b6bec90ab1f29bd42ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732426"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="b08dc-102">Método ICLRTaskManager::SetLocale</span><span class="sxs-lookup"><span data-stu-id="b08dc-102">ICLRTaskManager::SetLocale Method</span></span>

<span data-ttu-id="b08dc-103">Notifica o Common Language Runtime (CLR) que o host modificou o valor do identificador de localidade (que é mapeado para a cultura geográfica e idioma) na tarefa em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="b08dc-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b08dc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b08dc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b08dc-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b08dc-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="b08dc-106">no O valor do identificador de localidade que mapeia para a cultura geográfica e a linguagem recém atribuídas.</span><span class="sxs-lookup"><span data-stu-id="b08dc-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b08dc-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="b08dc-107">Return Value</span></span>  
  
|<span data-ttu-id="b08dc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b08dc-108">HRESULT</span></span>|<span data-ttu-id="b08dc-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="b08dc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b08dc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b08dc-110">S_OK</span></span>|<span data-ttu-id="b08dc-111">O método foi retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="b08dc-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b08dc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b08dc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b08dc-113">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="b08dc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b08dc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b08dc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b08dc-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="b08dc-115">The call timed out.</span></span>|  
|<span data-ttu-id="b08dc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b08dc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b08dc-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="b08dc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b08dc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b08dc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b08dc-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="b08dc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b08dc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b08dc-120">E_FAIL</span></span>|<span data-ttu-id="b08dc-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="b08dc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b08dc-122">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="b08dc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b08dc-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b08dc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b08dc-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="b08dc-124">Remarks</span></span>  

 <span data-ttu-id="b08dc-125">`SetLocale` Dá ao host uma oportunidade de executar qualquer mecanismo que ele possa ter para a sincronização de localidades.</span><span class="sxs-lookup"><span data-stu-id="b08dc-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b08dc-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b08dc-126">Requirements</span></span>  

 <span data-ttu-id="b08dc-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b08dc-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b08dc-128">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b08dc-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b08dc-129">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b08dc-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b08dc-130">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b08dc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b08dc-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="b08dc-131">See also</span></span>

- [<span data-ttu-id="b08dc-132">Interface ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b08dc-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b08dc-133">Interface ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b08dc-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b08dc-134">Interface IHostTask</span><span class="sxs-lookup"><span data-stu-id="b08dc-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b08dc-135">Interface IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b08dc-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
