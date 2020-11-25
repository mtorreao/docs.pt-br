---
title: Método ICLRRuntimeInfo::IsStarted
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 1dfeb6101a6b8e33ab2fe35f318087d7f1834b6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714881"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="0461a-102">Método ICLRRuntimeInfo::IsStarted</span><span class="sxs-lookup"><span data-stu-id="0461a-102">ICLRRuntimeInfo::IsStarted Method</span></span>

<span data-ttu-id="0461a-103">Indica se o tempo de execução foi iniciado (ou seja, se o [Método ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) foi chamado e teve êxito).</span><span class="sxs-lookup"><span data-stu-id="0461a-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0461a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0461a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0461a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0461a-105">Parameters</span></span>  

 `pbStarted`  
 <span data-ttu-id="0461a-106">[fora] `true` Se esse tempo de execução for iniciado; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="0461a-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="0461a-107">fora Retorna os sinalizadores que foram usados para iniciar o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0461a-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0461a-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="0461a-108">Return Value</span></span>  

 <span data-ttu-id="0461a-109">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="0461a-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0461a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0461a-110">HRESULT</span></span>|<span data-ttu-id="0461a-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="0461a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0461a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0461a-112">S_OK</span></span>|<span data-ttu-id="0461a-113">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="0461a-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="0461a-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0461a-114">E_NOTIMPL</span></span>|<span data-ttu-id="0461a-115">A versão Common Language Runtime (CLR) é anterior à versão do CLR no .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0461a-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0461a-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="0461a-116">Remarks</span></span>  

 <span data-ttu-id="0461a-117">Esse método não funciona com versões do CLR anteriores à versão do CLR no .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0461a-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0461a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0461a-118">Requirements</span></span>  

 <span data-ttu-id="0461a-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0461a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0461a-120">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="0461a-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0461a-121">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0461a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0461a-122">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0461a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0461a-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="0461a-123">See also</span></span>

- [<span data-ttu-id="0461a-124">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="0461a-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="0461a-125">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="0461a-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="0461a-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="0461a-126">Hosting</span></span>](index.md)
