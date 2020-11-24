---
title: Método ICLRAssemblyIdentityManager::IsStronglyNamed
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
ms.openlocfilehash: 9ac3b2ae349a696ba0cea1bad3e3484bb1c113fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679196"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="93aab-102">Método ICLRAssemblyIdentityManager::IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="93aab-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>

<span data-ttu-id="93aab-103">Obtém um valor que indica se o assembly especificado tem um nome forte.</span><span class="sxs-lookup"><span data-stu-id="93aab-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93aab-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="93aab-104">Syntax</span></span>  
  
```cpp  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93aab-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="93aab-105">Parameters</span></span>  

 `pwzAssemblyIdentity`  
 <span data-ttu-id="93aab-106">no Os dados de identidade de assembly Canonical opaco do assembly a ser avaliado.</span><span class="sxs-lookup"><span data-stu-id="93aab-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="93aab-107">[fora] `true` , se o assembly referenciado pelo `pwzAssemblyIdentity` parâmetro for fortemente nomeado; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="93aab-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93aab-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="93aab-108">Return Value</span></span>  
  
|<span data-ttu-id="93aab-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93aab-109">HRESULT</span></span>|<span data-ttu-id="93aab-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="93aab-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="93aab-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="93aab-111">S_OK</span></span>|<span data-ttu-id="93aab-112">O método foi retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="93aab-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="93aab-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="93aab-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="93aab-114">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="93aab-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="93aab-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="93aab-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="93aab-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="93aab-116">The call timed out.</span></span>|  
|<span data-ttu-id="93aab-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="93aab-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="93aab-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="93aab-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="93aab-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="93aab-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="93aab-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="93aab-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="93aab-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="93aab-121">E_FAIL</span></span>|<span data-ttu-id="93aab-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="93aab-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="93aab-123">Se um método retornar E_FAIL, o CLR não poderá mais ser usado no processo.</span><span class="sxs-lookup"><span data-stu-id="93aab-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="93aab-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="93aab-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93aab-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93aab-125">Requirements</span></span>  

 <span data-ttu-id="93aab-126">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93aab-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93aab-127">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="93aab-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93aab-128">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93aab-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93aab-129">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93aab-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93aab-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="93aab-130">See also</span></span>

- [<span data-ttu-id="93aab-131">Interface ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="93aab-131">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
