---
title: Método ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: f0a03ecce49bbc3c1c03d037c9be31a8e994259d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732080"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="2508a-102">Método ICLRRuntimeInfo::BindAsLegacyV2Runtime</span><span class="sxs-lookup"><span data-stu-id="2508a-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>

<span data-ttu-id="2508a-103">Associa o tempo de execução atual a todas as decisões de política de ativação da versão 2 do Common Language Runtime herdado (CLR).</span><span class="sxs-lookup"><span data-stu-id="2508a-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2508a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2508a-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2508a-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="2508a-105">Return Value</span></span>  

 <span data-ttu-id="2508a-106">Esse método retorna os HRESULTs específicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="2508a-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="2508a-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2508a-107">HRESULT</span></span>|<span data-ttu-id="2508a-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="2508a-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2508a-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="2508a-109">S_OK</span></span>|<span data-ttu-id="2508a-110">A associação foi bem-sucedida ou esse tempo de execução já estava associado ao tempo de execução da política de ativação do CLR versão 2 herdado.</span><span class="sxs-lookup"><span data-stu-id="2508a-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="2508a-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="2508a-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="2508a-112">Um tempo de execução diferente já estava associado à política de ativação do CLR versão 2 herdada.</span><span class="sxs-lookup"><span data-stu-id="2508a-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2508a-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="2508a-113">Remarks</span></span>  

 <span data-ttu-id="2508a-114">Se o tempo de execução atual já estiver associado a todas as decisões da política de ativação do CLR versão 2 herdadas (por exemplo, usando o `useLegacyV2RuntimeActivationPolicy` atributo no [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md) no arquivo de configuração), esse método não retornará um resultado de erro; em vez disso, o resultado será S_OK, assim como seria se o método tivesse associado com êxito a política de ativação herdada.</span><span class="sxs-lookup"><span data-stu-id="2508a-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2508a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2508a-115">Requirements</span></span>  

 <span data-ttu-id="2508a-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2508a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2508a-117">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="2508a-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2508a-118">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2508a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2508a-119">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2508a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2508a-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="2508a-120">See also</span></span>

- [<span data-ttu-id="2508a-121">Interface ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="2508a-121">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="2508a-122">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="2508a-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="2508a-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="2508a-123">Hosting</span></span>](index.md)
- [<span data-ttu-id="2508a-124">\<startup> Elementos</span><span class="sxs-lookup"><span data-stu-id="2508a-124">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
