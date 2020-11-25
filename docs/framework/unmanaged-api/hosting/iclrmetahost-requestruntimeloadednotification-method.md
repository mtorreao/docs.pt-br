---
title: Método ICLRMetaHost::RequestRuntimeLoadedNotification
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
ms.openlocfilehash: ac40e203cf7d32c1fe30c9915bac3171139403e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723274"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="cf952-102">Método ICLRMetaHost::RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="cf952-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>

<span data-ttu-id="cf952-103">Fornece uma função de retorno de chamada que tem a garantia de ser chamada quando uma versão Common Language Runtime (CLR) é carregada pela primeira vez, mas ainda não foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="cf952-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="cf952-104">Esse método substitui a função [LockClrVersion](lockclrversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cf952-104">This method supersedes the [LockClrVersion](lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf952-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cf952-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf952-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cf952-106">Parameters</span></span>  

 `pCallbackFunction`  
 <span data-ttu-id="cf952-107">no A função de retorno de chamada que é invocada quando um novo tempo de execução é carregado.</span><span class="sxs-lookup"><span data-stu-id="cf952-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf952-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="cf952-108">Return Value</span></span>  

 <span data-ttu-id="cf952-109">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="cf952-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cf952-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf952-110">HRESULT</span></span>|<span data-ttu-id="cf952-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="cf952-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cf952-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf952-112">S_OK</span></span>|<span data-ttu-id="cf952-113">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="cf952-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="cf952-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="cf952-114">E_POINTER</span></span>|<span data-ttu-id="cf952-115">`pCallbackFunction` é nulo.</span><span class="sxs-lookup"><span data-stu-id="cf952-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf952-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="cf952-116">Remarks</span></span>  

 <span data-ttu-id="cf952-117">O retorno de chamada funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cf952-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="cf952-118">O retorno de chamada é invocado somente quando um tempo de execução é carregado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="cf952-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="cf952-119">O retorno de chamada não é invocado para cargas reentrante do mesmo tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="cf952-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="cf952-120">Para cargas de tempo de execução não reentrante, as chamadas para a função de retorno de chamada são serializadas.</span><span class="sxs-lookup"><span data-stu-id="cf952-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="cf952-121">A função de retorno de chamada tem o seguinte protótipo:</span><span class="sxs-lookup"><span data-stu-id="cf952-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="cf952-122">Os protótipos de função de retorno de chamada são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="cf952-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="cf952-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="cf952-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="cf952-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="cf952-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="cf952-125">Se o host pretende carregar ou fazer com que outro tempo de execução seja carregado de maneira reentrante, os `pfnCallbackThreadSet` `pfnCallbackThreadUnset` parâmetros e fornecidos na função de retorno de chamada devem ser usados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cf952-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="cf952-126">`pfnCallbackThreadSet` deve ser chamado pelo thread que pode causar uma carga de tempo de execução antes que essa carga seja tentada.</span><span class="sxs-lookup"><span data-stu-id="cf952-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="cf952-127">`pfnCallbackThreadUnset` deve ser chamado quando o thread não causar mais tal carga de tempo de execução (e antes de retornar do retorno de chamada inicial).</span><span class="sxs-lookup"><span data-stu-id="cf952-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="cf952-128">`pfnCallbackThreadSet` e `pfnCallbackThreadUnset` que não são reentrante.</span><span class="sxs-lookup"><span data-stu-id="cf952-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf952-129">Os aplicativos host não devem chamar `pfnCallbackThreadSet` e `pfnCallbackThreadUnset` fora do escopo do `pCallbackFunction` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="cf952-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf952-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf952-130">Requirements</span></span>  

 <span data-ttu-id="cf952-131">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf952-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf952-132">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="cf952-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cf952-133">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf952-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf952-134">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf952-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf952-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="cf952-135">See also</span></span>

- [<span data-ttu-id="cf952-136">Interface ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="cf952-136">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="cf952-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="cf952-137">Hosting</span></span>](index.md)
