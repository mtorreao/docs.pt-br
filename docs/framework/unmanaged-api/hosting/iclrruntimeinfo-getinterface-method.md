---
title: Método ICLRRuntimeInfo::GetInterface
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
ms.openlocfilehash: 192163ed8af680e39f7f3a03aee3f46546bc7450
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732067"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="ba8ba-102">Método ICLRRuntimeInfo::GetInterface</span><span class="sxs-lookup"><span data-stu-id="ba8ba-102">ICLRRuntimeInfo::GetInterface Method</span></span>

<span data-ttu-id="ba8ba-103">Carrega o CLR no processo atual e retorna ponteiros de interface de tempo de execução, como [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)e [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ba8ba-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md), and [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="ba8ba-104">Esse método substitui todas as `CorBindTo` funções \* na seção [funções de Hospedagem de CLR preteridas](deprecated-clr-hosting-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="ba8ba-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8ba-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ba8ba-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba8ba-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ba8ba-106">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="ba8ba-107">no A interface CLSID para a coclass.</span><span class="sxs-lookup"><span data-stu-id="ba8ba-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="ba8ba-108">no O IID da interface solicitada `rclsid` .</span><span class="sxs-lookup"><span data-stu-id="ba8ba-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="ba8ba-109">fora Um ponteiro para a interface consultada.</span><span class="sxs-lookup"><span data-stu-id="ba8ba-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba8ba-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="ba8ba-110">Return Value</span></span>  

 <span data-ttu-id="ba8ba-111">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="ba8ba-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ba8ba-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba8ba-112">HRESULT</span></span>|<span data-ttu-id="ba8ba-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="ba8ba-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba8ba-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba8ba-114">S_OK</span></span>|<span data-ttu-id="ba8ba-115">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="ba8ba-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="ba8ba-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ba8ba-116">E_POINTER</span></span>|<span data-ttu-id="ba8ba-117">`ppUnk` é nulo.</span><span class="sxs-lookup"><span data-stu-id="ba8ba-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="ba8ba-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ba8ba-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ba8ba-119">Não há memória suficiente disponível para lidar com a solicitação.</span><span class="sxs-lookup"><span data-stu-id="ba8ba-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="ba8ba-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="ba8ba-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="ba8ba-121">Um tempo de execução diferente já estava associado à política de ativação do CLR versão 2 herdada.</span><span class="sxs-lookup"><span data-stu-id="ba8ba-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba8ba-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="ba8ba-122">Remarks</span></span>  

 <span data-ttu-id="ba8ba-123">Esse método faz com que o CLR seja carregado, mas não inicializado.</span><span class="sxs-lookup"><span data-stu-id="ba8ba-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="ba8ba-124">A tabela a seguir mostra as combinações com suporte para o `rclsid` e o `riid` .</span><span class="sxs-lookup"><span data-stu-id="ba8ba-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="ba8ba-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="ba8ba-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="ba8ba-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="ba8ba-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="ba8ba-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="ba8ba-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="ba8ba-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="ba8ba-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="ba8ba-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ba8ba-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="ba8ba-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ba8ba-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="ba8ba-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ba8ba-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="ba8ba-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ba8ba-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="ba8ba-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="ba8ba-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="ba8ba-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="ba8ba-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="ba8ba-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="ba8ba-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="ba8ba-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ba8ba-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="ba8ba-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ba8ba-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="ba8ba-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ba8ba-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba8ba-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba8ba-139">Requirements</span></span>  

 <span data-ttu-id="ba8ba-140">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba8ba-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba8ba-141">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="ba8ba-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ba8ba-142">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba8ba-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba8ba-143">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8ba-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8ba-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="ba8ba-144">See also</span></span>

- [<span data-ttu-id="ba8ba-145">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="ba8ba-145">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="ba8ba-146">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="ba8ba-146">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="ba8ba-147">Hosting</span><span class="sxs-lookup"><span data-stu-id="ba8ba-147">Hosting</span></span>](index.md)
