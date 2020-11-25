---
title: Método ICLRRuntimeHost::GetCLRControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
ms.openlocfilehash: 928ac05fbd3a19a17e7f37674b2a75f8bc799fc6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728860"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="515f5-102">Método ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="515f5-102">ICLRRuntimeHost::GetCLRControl Method</span></span>

<span data-ttu-id="515f5-103">Obtém um ponteiro de interface do tipo [interface ICLRControl](iclrcontrol-interface.md) que os hosts podem usar para personalizar aspectos do Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="515f5-103">Gets an interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="515f5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="515f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="515f5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="515f5-105">Parameters</span></span>  

 `pCLRControl`  
 <span data-ttu-id="515f5-106">fora Um ponteiro de interface do tipo [interface ICLRControl](iclrcontrol-interface.md) que permite que os hosts configurem aspectos adicionais do CLR.</span><span class="sxs-lookup"><span data-stu-id="515f5-106">[out] An interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="515f5-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="515f5-107">Return Value</span></span>  
  
|<span data-ttu-id="515f5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="515f5-108">HRESULT</span></span>|<span data-ttu-id="515f5-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="515f5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="515f5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="515f5-110">S_OK</span></span>|<span data-ttu-id="515f5-111">`GetCLRControl` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="515f5-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="515f5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="515f5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="515f5-113">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="515f5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="515f5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="515f5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="515f5-115">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="515f5-115">The call timed out.</span></span>|  
|<span data-ttu-id="515f5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="515f5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="515f5-117">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="515f5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="515f5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="515f5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="515f5-119">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="515f5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="515f5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="515f5-120">E_FAIL</span></span>|<span data-ttu-id="515f5-121">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="515f5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="515f5-122">Se um método retornar E_FAIL, o CLR não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="515f5-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="515f5-123">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="515f5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="515f5-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="515f5-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="515f5-125">O CLR já foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="515f5-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="515f5-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="515f5-126">Remarks</span></span>  

 <span data-ttu-id="515f5-127">`ICLRControl` fornece o método de [método GetCLRManager](iclrcontrol-getclrmanager-method.md) , que permite que o host obtenha um ponteiro de interface para um dos tipos de gerente.</span><span class="sxs-lookup"><span data-stu-id="515f5-127">`ICLRControl` provides the [GetCLRManager Method](iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="515f5-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="515f5-128">Requirements</span></span>  

 <span data-ttu-id="515f5-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="515f5-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="515f5-130">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="515f5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="515f5-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="515f5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="515f5-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="515f5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515f5-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="515f5-133">See also</span></span>

- [<span data-ttu-id="515f5-134">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="515f5-134">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="515f5-135">Interface ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="515f5-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
