---
title: Método ICLRPolicyManager::SetUnhandledExceptionPolicy
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 1088374c9df18ded38b44384be44de245f0bd403
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728947"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="f8895-102">Método ICLRPolicyManager::SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="f8895-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>

<span data-ttu-id="f8895-103">Especifica o comportamento do Common Language Runtime (CLR) quando ocorre uma exceção sem tratamento.</span><span class="sxs-lookup"><span data-stu-id="f8895-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8895-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f8895-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8895-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f8895-105">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="f8895-106">no Um dos valores de [EClrUnhandledException](eclrunhandledexception-enumeration.md) , indicando se o comportamento é definido pelo CLR ou pelo host.</span><span class="sxs-lookup"><span data-stu-id="f8895-106">[in] One of the [EClrUnhandledException](eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8895-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f8895-107">Return Value</span></span>  
  
|<span data-ttu-id="f8895-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8895-108">HRESULT</span></span>|<span data-ttu-id="f8895-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="f8895-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8895-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8895-110">S_OK</span></span>|<span data-ttu-id="f8895-111">`SetUnhandledExceptionPolicy` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="f8895-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="f8895-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f8895-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f8895-113">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="f8895-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f8895-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f8895-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f8895-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="f8895-115">The call timed out.</span></span>|  
|<span data-ttu-id="f8895-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f8895-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f8895-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="f8895-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f8895-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f8895-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f8895-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="f8895-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f8895-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f8895-120">E_FAIL</span></span>|<span data-ttu-id="f8895-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="f8895-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f8895-122">Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="f8895-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f8895-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f8895-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8895-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="f8895-124">Remarks</span></span>  

 <span data-ttu-id="f8895-125">Por padrão, o CLR é o manipulador final para todas as exceções sem tratamento e seu comportamento padrão é subdividir o processo.</span><span class="sxs-lookup"><span data-stu-id="f8895-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="f8895-126">O host pode alterar esse comportamento definindo o `policy` valor como eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="f8895-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="f8895-127">Esse valor permite que o host implemente seu próprio comportamento padrão, como nas versões anteriores do CLR.</span><span class="sxs-lookup"><span data-stu-id="f8895-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8895-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8895-128">Requirements</span></span>  

 <span data-ttu-id="f8895-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8895-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8895-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f8895-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8895-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8895-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8895-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8895-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8895-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="f8895-133">See also</span></span>

- [<span data-ttu-id="f8895-134">Enumeração EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="f8895-134">EClrUnhandledException Enumeration</span></span>](eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="f8895-135">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="f8895-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f8895-136">Interface ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f8895-136">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="f8895-137">Interface IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f8895-137">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
