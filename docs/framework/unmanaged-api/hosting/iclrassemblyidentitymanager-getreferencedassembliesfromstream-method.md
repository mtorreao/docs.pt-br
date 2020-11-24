---
title: Método ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
ms.openlocfilehash: a5e71d6ca90c8d0aa489176eb5a90bfe6896b1cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679307"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="a3a62-102">Método ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="a3a62-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>

<span data-ttu-id="a3a62-103">Obtém um ponteiro para um objeto [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) que contém dados de identidade de assembly para os assemblies referenciados pelo assembly no fluxo especificado.</span><span class="sxs-lookup"><span data-stu-id="a3a62-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a62-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a3a62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3a62-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a3a62-105">Parameters</span></span>  

 `pStream`  
 <span data-ttu-id="a3a62-106">no Um ponteiro de interface para um `IStream` que contém o assembly a ser avaliado.</span><span class="sxs-lookup"><span data-stu-id="a3a62-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a3a62-107">no Fornecido para extensibilidade futura.</span><span class="sxs-lookup"><span data-stu-id="a3a62-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="a3a62-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT é o único valor para o qual a versão atual do Common Language Runtime (CLR) dá suporte.</span><span class="sxs-lookup"><span data-stu-id="a3a62-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="a3a62-109">no Um ponteiro para um objeto [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que contém dados de identidade de assembly para os assemblies a serem excluídos `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="a3a62-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="a3a62-110">fora Um ponteiro para o endereço de um `ICLRReferenceAssemblyEnum` objeto que contém dados de identidade de assembly para os assemblies referenciados pelo assembly no `pStream` , excluindo os assemblies no `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="a3a62-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3a62-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="a3a62-111">Return Value</span></span>  
  
|<span data-ttu-id="a3a62-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3a62-112">HRESULT</span></span>|<span data-ttu-id="a3a62-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="a3a62-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3a62-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3a62-114">S_OK</span></span>|<span data-ttu-id="a3a62-115">O método foi retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a3a62-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="a3a62-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3a62-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3a62-117">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="a3a62-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3a62-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3a62-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3a62-119">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="a3a62-119">The call timed out.</span></span>|  
|<span data-ttu-id="a3a62-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3a62-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3a62-121">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="a3a62-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3a62-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3a62-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3a62-123">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="a3a62-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3a62-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3a62-124">E_FAIL</span></span>|<span data-ttu-id="a3a62-125">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="a3a62-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3a62-126">Se um método retornar E_FAIL, o CLR não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="a3a62-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3a62-127">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a3a62-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3a62-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="a3a62-128">Remarks</span></span>  

 <span data-ttu-id="a3a62-129">O chamador pode optar por excluir um conjunto de referências de assembly conhecidas da lista retornada.</span><span class="sxs-lookup"><span data-stu-id="a3a62-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="a3a62-130">Esse conjunto é definido por `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="a3a62-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3a62-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3a62-131">Requirements</span></span>  

 <span data-ttu-id="a3a62-132">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3a62-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3a62-133">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a3a62-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3a62-134">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3a62-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3a62-135">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3a62-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a62-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3a62-136">See also</span></span>

- [<span data-ttu-id="a3a62-137">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="a3a62-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a3a62-138">Interface ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="a3a62-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a3a62-139">Interface ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="a3a62-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
