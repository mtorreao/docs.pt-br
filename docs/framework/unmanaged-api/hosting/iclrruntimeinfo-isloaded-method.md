---
title: Método ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: 66ae74deba9ceab9d1ea6b2c0b96a87bf44f32ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714920"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="c90f1-102">Método ICLRRuntimeInfo::IsLoaded</span><span class="sxs-lookup"><span data-stu-id="c90f1-102">ICLRRuntimeInfo::IsLoaded Method</span></span>

<span data-ttu-id="c90f1-103">Indica se o Common Language Runtime (CLR) associado à interface [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) é carregado em um processo.</span><span class="sxs-lookup"><span data-stu-id="c90f1-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="c90f1-104">Um tempo de execução pode ser carregado sem também ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="c90f1-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c90f1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c90f1-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c90f1-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c90f1-106">Parameters</span></span>  

 `hndProcess`  
 <span data-ttu-id="c90f1-107">no Um identificador para o processo.</span><span class="sxs-lookup"><span data-stu-id="c90f1-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="c90f1-108">[fora] `true` Se o CLR for carregado no processo; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="c90f1-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c90f1-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="c90f1-109">Return Value</span></span>  

 <span data-ttu-id="c90f1-110">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="c90f1-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c90f1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c90f1-111">HRESULT</span></span>|<span data-ttu-id="c90f1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c90f1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c90f1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c90f1-113">S_OK</span></span>|<span data-ttu-id="c90f1-114">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="c90f1-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c90f1-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c90f1-115">E_POINTER</span></span>|<span data-ttu-id="c90f1-116">`pbLoaded` é nulo.</span><span class="sxs-lookup"><span data-stu-id="c90f1-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c90f1-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="c90f1-117">Remarks</span></span>  

 <span data-ttu-id="c90f1-118">Esse método é compatível com versões anteriores com as seguintes funções e interfaces:</span><span class="sxs-lookup"><span data-stu-id="c90f1-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="c90f1-119">Interface [ICorRuntimeHost](icorruntimehost-interface.md) (na API de hospedagem do .NET Framework versão 1).</span><span class="sxs-lookup"><span data-stu-id="c90f1-119">[ICorRuntimeHost](icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="c90f1-120">Interface [ICLRRuntimeHost](iclrruntimehost-interface.md) (na API de hospedagem .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="c90f1-120">[ICLRRuntimeHost](iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="c90f1-121">Funções preteridas `CorBindTo*` (consulte [funções de Hospedagem de CLR preteridas](deprecated-clr-hosting-functions.md) na API de hospedagem .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="c90f1-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="c90f1-122">Um host pode chamar uma das funções preteridas `CorBindTo*` , como a função [CorBindToRuntime](corbindtoruntime-function.md) , para instanciar uma versão específica do CLR.</span><span class="sxs-lookup"><span data-stu-id="c90f1-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="c90f1-123">O host poderia então chamar o método [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) e especificar o mesmo número de versão para obter uma interface [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c90f1-123">The host could then call the [ICLRMetaHost::GetRuntime](iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="c90f1-124">Se o host chamar o `IsLoaded` método na interface [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) retornada, `pbLoaded` retornará `true` ; caso contrário, retornará `false` .</span><span class="sxs-lookup"><span data-stu-id="c90f1-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c90f1-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c90f1-125">Requirements</span></span>  

 <span data-ttu-id="c90f1-126">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c90f1-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c90f1-127">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="c90f1-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c90f1-128">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c90f1-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c90f1-129">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c90f1-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90f1-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="c90f1-130">See also</span></span>

- [<span data-ttu-id="c90f1-131">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="c90f1-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="c90f1-132">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="c90f1-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="c90f1-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="c90f1-133">Hosting</span></span>](index.md)
