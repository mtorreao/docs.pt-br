---
title: Método ICLRValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
ms.openlocfilehash: a3f52deab4d0c8ca56fae2e65912217e51abe58a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715856"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="0422f-102">Método ICLRValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="0422f-102">ICLRValidator::FormatEventInfo Method</span></span>

<span data-ttu-id="0422f-103">Obtém uma mensagem detalhada sobre o erro de validação especificado.</span><span class="sxs-lookup"><span data-stu-id="0422f-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0422f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0422f-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0422f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0422f-105">Parameters</span></span>  

 `hVECode`  
 <span data-ttu-id="0422f-106">no O valor HRESULT que foi passado para o manipulador de erro de validação.</span><span class="sxs-lookup"><span data-stu-id="0422f-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="0422f-107">no Uma `VEContext` instância que contém informações de contexto sobre os erros de validação.</span><span class="sxs-lookup"><span data-stu-id="0422f-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="0422f-108">[entrada, saída] A mensagem de erro amigável.</span><span class="sxs-lookup"><span data-stu-id="0422f-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="0422f-109">no O comprimento máximo da mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="0422f-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="0422f-110">no Uma matriz segura de parâmetros adicionais a serem usados na mensagem.</span><span class="sxs-lookup"><span data-stu-id="0422f-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0422f-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="0422f-111">Return Value</span></span>  
  
|<span data-ttu-id="0422f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0422f-112">HRESULT</span></span>|<span data-ttu-id="0422f-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="0422f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0422f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0422f-114">S_OK</span></span>|<span data-ttu-id="0422f-115">`FormatEventInfo` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="0422f-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="0422f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0422f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0422f-117">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="0422f-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0422f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0422f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0422f-119">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="0422f-119">The call timed out.</span></span>|  
|<span data-ttu-id="0422f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0422f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0422f-121">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="0422f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0422f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0422f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0422f-123">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="0422f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0422f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0422f-124">E_FAIL</span></span>|<span data-ttu-id="0422f-125">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="0422f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0422f-126">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="0422f-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0422f-127">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0422f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0422f-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0422f-128">Requirements</span></span>  

 <span data-ttu-id="0422f-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0422f-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0422f-130">**Cabeçalho:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="0422f-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="0422f-131">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0422f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0422f-132">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0422f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0422f-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="0422f-133">See also</span></span>

- [<span data-ttu-id="0422f-134">Interface ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="0422f-134">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="0422f-135">Interface ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="0422f-135">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
