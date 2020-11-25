---
title: Método ICorRuntimeHost::CloseEnum
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
ms.openlocfilehash: d3748621474373fee8248496d48414ff67c699d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715688"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="f3cb6-102">Método ICorRuntimeHost::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="f3cb6-102">ICorRuntimeHost::CloseEnum Method</span></span>

<span data-ttu-id="f3cb6-103">Redefine um enumerador de domínio de volta para o início da lista de domínios.</span><span class="sxs-lookup"><span data-stu-id="f3cb6-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3cb6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f3cb6-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3cb6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f3cb6-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="f3cb6-106">no O enumerador a ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="f3cb6-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3cb6-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f3cb6-107">Return Value</span></span>  
  
|<span data-ttu-id="f3cb6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3cb6-108">HRESULT</span></span>|<span data-ttu-id="f3cb6-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3cb6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3cb6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3cb6-110">S_OK</span></span>|<span data-ttu-id="f3cb6-111">A operação foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f3cb6-111">The operation was successful.</span></span>|  
|<span data-ttu-id="f3cb6-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f3cb6-112">S_FALSE</span></span>|<span data-ttu-id="f3cb6-113">Falha ao concluir a operação.</span><span class="sxs-lookup"><span data-stu-id="f3cb6-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f3cb6-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3cb6-114">E_FAIL</span></span>|<span data-ttu-id="f3cb6-115">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="f3cb6-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f3cb6-116">Se um método retornar E_FAIL, o Common Language Runtime (CLR) não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="f3cb6-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="f3cb6-117">As chamadas subsequentes para qualquer API de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f3cb6-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f3cb6-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3cb6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3cb6-119">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="f3cb6-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3cb6-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3cb6-120">Requirements</span></span>  

 <span data-ttu-id="f3cb6-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3cb6-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3cb6-122">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f3cb6-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3cb6-123">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3cb6-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3cb6-124">**Versões do .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="f3cb6-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3cb6-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="f3cb6-125">See also</span></span>

- [<span data-ttu-id="f3cb6-126">Função CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="f3cb6-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="f3cb6-127">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f3cb6-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
