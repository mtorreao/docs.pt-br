---
title: Método ICorRuntimeHost::CreateDomainSetup
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 1be7eee5c2591f26c33572446080a4fa4b3b929d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723890"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="e00fb-102">Método ICorRuntimeHost::CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="e00fb-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>

<span data-ttu-id="e00fb-103">Obtém um ponteiro de interface do tipo IAppDomainSetup para uma <xref:System.AppDomainSetup?displayProperty=nameWithType> instância.</span><span class="sxs-lookup"><span data-stu-id="e00fb-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="e00fb-104">`IAppDomainSetup` fornece métodos para configurar aspectos de um domínio de aplicativo antes de sua criação.</span><span class="sxs-lookup"><span data-stu-id="e00fb-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e00fb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e00fb-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e00fb-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e00fb-106">Parameters</span></span>  

 `pAppDomainSetup`  
 <span data-ttu-id="e00fb-107">fora Um ponteiro de interface para uma <xref:System.AppDomainSetup?displayProperty=nameWithType> instância.</span><span class="sxs-lookup"><span data-stu-id="e00fb-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="e00fb-108">Esse parâmetro é digitado como `IUnknown` , de modo que os chamadores geralmente devem chamar `QueryInterface` esse ponteiro para obter um ponteiro de interface do tipo `IAppDomainSetup` .</span><span class="sxs-lookup"><span data-stu-id="e00fb-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e00fb-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="e00fb-109">Return Value</span></span>  
  
|<span data-ttu-id="e00fb-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e00fb-110">HRESULT</span></span>|<span data-ttu-id="e00fb-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="e00fb-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e00fb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e00fb-112">S_OK</span></span>|<span data-ttu-id="e00fb-113">A operação foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="e00fb-113">The operation was successful.</span></span>|  
|<span data-ttu-id="e00fb-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e00fb-114">S_FALSE</span></span>|<span data-ttu-id="e00fb-115">Falha ao concluir a operação.</span><span class="sxs-lookup"><span data-stu-id="e00fb-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e00fb-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e00fb-116">E_FAIL</span></span>|<span data-ttu-id="e00fb-117">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="e00fb-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e00fb-118">Se um método retornar E_FAIL, o Common Language Runtime (CLR) não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="e00fb-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e00fb-119">As chamadas subsequentes para qualquer API de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e00fb-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e00fb-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e00fb-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e00fb-121">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="e00fb-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e00fb-122">Comentários</span><span class="sxs-lookup"><span data-stu-id="e00fb-122">Remarks</span></span>  

 <span data-ttu-id="e00fb-123">O ponteiro retornado desse método normalmente é passado como um parâmetro para o método [CreateDomainEx](icorruntimehost-createdomainex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e00fb-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e00fb-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e00fb-124">Requirements</span></span>  

 <span data-ttu-id="e00fb-125">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e00fb-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e00fb-126">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e00fb-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e00fb-127">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e00fb-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e00fb-128">**Versão do .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e00fb-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e00fb-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="e00fb-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="e00fb-130">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e00fb-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
