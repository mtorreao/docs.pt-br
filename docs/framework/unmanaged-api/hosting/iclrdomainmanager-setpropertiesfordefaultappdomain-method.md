---
title: Método ICLRDomainManager::SetPropertiesForDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: b5577d0444caf14fb47d9d7e2de60a8399378db7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702128"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="79c0f-102">Método ICLRDomainManager::SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="79c0f-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>

<span data-ttu-id="79c0f-103">Define as propriedades que serão usadas para inicializar o domínio de aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="79c0f-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c0f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="79c0f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79c0f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="79c0f-105">Parameters</span></span>  

 `nProperties`  
 <span data-ttu-id="79c0f-106">no O número de entradas no `pwszPropertyNames` e no `pwszPropertyValues` .</span><span class="sxs-lookup"><span data-stu-id="79c0f-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="79c0f-107">no Uma matriz de nomes de propriedade ou NULL se não houver propriedades.</span><span class="sxs-lookup"><span data-stu-id="79c0f-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="79c0f-108">Atualmente, o único nome de propriedade reconhecido por esse método é "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="79c0f-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="79c0f-109">no Uma matriz de valores de propriedade ou NULL se não houver nenhuma propriedade.</span><span class="sxs-lookup"><span data-stu-id="79c0f-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79c0f-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="79c0f-110">Return Value</span></span>  

 <span data-ttu-id="79c0f-111">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="79c0f-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="79c0f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79c0f-112">HRESULT</span></span>|<span data-ttu-id="79c0f-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="79c0f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79c0f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="79c0f-114">S_OK</span></span>|<span data-ttu-id="79c0f-115">O método foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="79c0f-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="79c0f-116">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="79c0f-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="79c0f-117">`pwszPropertyNames` inclui um nome de propriedade que não é reconhecido por este método.</span><span class="sxs-lookup"><span data-stu-id="79c0f-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79c0f-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="79c0f-118">Remarks</span></span>  

 <span data-ttu-id="79c0f-119">O valor da propriedade para "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" é uma lista de ASSEMBLIES que têm o <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA) com o <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> sinalizador, que deve se tornar visível para chamadores parcialmente confiáveis no domínio do aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="79c0f-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79c0f-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79c0f-120">Requirements</span></span>  

 <span data-ttu-id="79c0f-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79c0f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79c0f-122">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="79c0f-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="79c0f-123">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79c0f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79c0f-124">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79c0f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c0f-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="79c0f-125">See also</span></span>

- [<span data-ttu-id="79c0f-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="79c0f-126">Hosting</span></span>](index.md)
- [<span data-ttu-id="79c0f-127">Interface ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="79c0f-127">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
