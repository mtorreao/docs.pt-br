---
title: Método ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
ms.openlocfilehash: cfc384a71ac7e91181bdec09f0d385bacbe31753
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716662"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="c815c-102">Método ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="c815c-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>

<span data-ttu-id="c815c-103">Obtém um ponteiro de interface para uma instância de [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) da lista fornecida de identidades de assembly parciais.</span><span class="sxs-lookup"><span data-stu-id="c815c-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c815c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c815c-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c815c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c815c-105">Parameters</span></span>  

 `ppwzAssemblyReferences`  
 <span data-ttu-id="c815c-106">no Uma matriz de cadeias de caracteres terminadas em nulo no formato "nome, propriedade = valor..." Isso especifica uma lista de identidades de assembly parciais.</span><span class="sxs-lookup"><span data-stu-id="c815c-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="c815c-107">no O número de itens em `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="c815c-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="c815c-108">fora Um ponteiro de interface para um `ICLRAssemblyReferenceList` objeto que contém os dados de identidade do assembly para a lista de assemblies especificados em `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="c815c-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c815c-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="c815c-109">Return Value</span></span>  
  
|<span data-ttu-id="c815c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c815c-110">HRESULT</span></span>|<span data-ttu-id="c815c-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="c815c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c815c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c815c-112">S_OK</span></span>|<span data-ttu-id="c815c-113">O método foi retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="c815c-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="c815c-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c815c-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c815c-115">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="c815c-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c815c-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c815c-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c815c-117">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="c815c-117">The call timed out.</span></span>|  
|<span data-ttu-id="c815c-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c815c-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c815c-119">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="c815c-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c815c-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c815c-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c815c-121">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="c815c-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c815c-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c815c-122">E_FAIL</span></span>|<span data-ttu-id="c815c-123">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="c815c-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c815c-124">Se um método retornar E_FAIL, o CLR não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="c815c-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c815c-125">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c815c-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c815c-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c815c-126">Requirements</span></span>  

 <span data-ttu-id="c815c-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c815c-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c815c-128">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c815c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c815c-129">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c815c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c815c-130">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c815c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c815c-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="c815c-131">See also</span></span>

- [<span data-ttu-id="c815c-132">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="c815c-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c815c-133">Interface ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="c815c-133">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
