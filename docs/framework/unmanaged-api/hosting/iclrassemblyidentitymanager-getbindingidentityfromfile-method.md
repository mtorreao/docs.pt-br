---
title: Método ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
ms.openlocfilehash: 443acfa77dc8103008263f19bed116d02e7ea676
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716712"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="aa392-102">Método ICLRAssemblyIdentityManager::GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="aa392-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>

<span data-ttu-id="aa392-103">Obtém os dados de associação de identidade do assembly para o assembly no caminho de arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="aa392-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa392-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aa392-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa392-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="aa392-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="aa392-106">no O caminho para o arquivo a ser avaliado.</span><span class="sxs-lookup"><span data-stu-id="aa392-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="aa392-107">no Um valor da enumeração [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) que indica o tipo de identidade de um assembly.</span><span class="sxs-lookup"><span data-stu-id="aa392-107">[in] A value of the [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="aa392-108">Fornecido para extensibilidade futura.</span><span class="sxs-lookup"><span data-stu-id="aa392-108">Provided for future extensibility.</span></span> <span data-ttu-id="aa392-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT é o único valor ao qual a versão do Common Language Runtime (CLR) 2,0 dá suporte.</span><span class="sxs-lookup"><span data-stu-id="aa392-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="aa392-110">fora Um buffer que contém os dados de identidade do assembly opaco.</span><span class="sxs-lookup"><span data-stu-id="aa392-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="aa392-111">[entrada, saída] Um ponteiro para o tamanho de `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="aa392-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa392-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="aa392-112">Return Value</span></span>  
  
|<span data-ttu-id="aa392-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa392-113">HRESULT</span></span>|<span data-ttu-id="aa392-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="aa392-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa392-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa392-115">S_OK</span></span>|<span data-ttu-id="aa392-116">O método foi retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="aa392-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="aa392-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="aa392-117">E_INVALIDARG</span></span>|<span data-ttu-id="aa392-118">O fornecido `pwzFilePath` é nulo.</span><span class="sxs-lookup"><span data-stu-id="aa392-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="aa392-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="aa392-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="aa392-120">O tamanho de `pwzBuffer` é muito pequeno.</span><span class="sxs-lookup"><span data-stu-id="aa392-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="aa392-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aa392-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aa392-122">O CLR não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="aa392-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aa392-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aa392-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aa392-124">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="aa392-124">The call timed out.</span></span>|  
|<span data-ttu-id="aa392-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa392-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aa392-126">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="aa392-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aa392-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aa392-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aa392-128">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="aa392-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aa392-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa392-129">E_FAIL</span></span>|<span data-ttu-id="aa392-130">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="aa392-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aa392-131">Se um método retornar E_FAIL, o CLR não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="aa392-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aa392-132">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aa392-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa392-133">Comentários</span><span class="sxs-lookup"><span data-stu-id="aa392-133">Remarks</span></span>  

 <span data-ttu-id="aa392-134">`GetBindingIdentityFromFile` normalmente é chamado duas vezes.</span><span class="sxs-lookup"><span data-stu-id="aa392-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="aa392-135">A primeira chamada fornece um valor nulo para `pwzBuffer` , e o método retorna o tamanho apropriado em `pcchBufferSize` .</span><span class="sxs-lookup"><span data-stu-id="aa392-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="aa392-136">A segunda chamada fornece um buffer adequadamente alocado e o método retorna com os dados reais do buffer após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="aa392-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa392-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa392-137">Requirements</span></span>  

 <span data-ttu-id="aa392-138">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa392-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa392-139">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aa392-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa392-140">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa392-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa392-141">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa392-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa392-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="aa392-142">See also</span></span>

- [<span data-ttu-id="aa392-143">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="aa392-143">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="aa392-144">Interface ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="aa392-144">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="aa392-145">Interface ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="aa392-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
