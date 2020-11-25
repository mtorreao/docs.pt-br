---
title: Método ICLRHostProtectionManager::SetEagerSerializeGrantSets
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
ms.openlocfilehash: 9ce4a5e042e838da8e9eba614f26e35b38af56c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714127"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="61ef9-102">Método ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="61ef9-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>

<span data-ttu-id="61ef9-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="61ef9-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ef9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="61ef9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="61ef9-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="61ef9-105">Return Value</span></span>  
  
|<span data-ttu-id="61ef9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61ef9-106">HRESULT</span></span>|<span data-ttu-id="61ef9-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="61ef9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61ef9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="61ef9-108">S_OK</span></span>|<span data-ttu-id="61ef9-109">`SetEagerSerializeGrantSets` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="61ef9-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="61ef9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="61ef9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="61ef9-111">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="61ef9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="61ef9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="61ef9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="61ef9-113">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="61ef9-113">The call timed out.</span></span>|  
|<span data-ttu-id="61ef9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="61ef9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="61ef9-115">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="61ef9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="61ef9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="61ef9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="61ef9-117">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="61ef9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="61ef9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61ef9-118">E_FAIL</span></span>|<span data-ttu-id="61ef9-119">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="61ef9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61ef9-120">Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="61ef9-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="61ef9-121">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="61ef9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61ef9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61ef9-122">Requirements</span></span>  

 <span data-ttu-id="61ef9-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61ef9-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61ef9-124">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="61ef9-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61ef9-125">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61ef9-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61ef9-126">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61ef9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ef9-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="61ef9-127">See also</span></span>

- [<span data-ttu-id="61ef9-128">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="61ef9-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="61ef9-129">Interface ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="61ef9-129">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
