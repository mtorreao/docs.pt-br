---
title: Método IHostMemoryManager::CreateMAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 79580170d544cd3763992a4bc67fd20e3446bb1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685715"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="a27d5-102">Método IHostMemoryManager::CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="a27d5-102">IHostMemoryManager::CreateMAlloc Method</span></span>

<span data-ttu-id="a27d5-103">Obtém um ponteiro de interface para uma instância de [IHostMAlloc](ihostmalloc-interface.md) que é usada para fazer solicitações de alocação de um heap criado pelo host.</span><span class="sxs-lookup"><span data-stu-id="a27d5-103">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a27d5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a27d5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a27d5-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a27d5-105">Parameters</span></span>  

 `dwMallocType`  
 <span data-ttu-id="a27d5-106">no Uma combinação de sinalizadores de [MALLOC_TYPE](malloc-type-enumeration.md) que especifica as características da memória que está sendo alocada.</span><span class="sxs-lookup"><span data-stu-id="a27d5-106">[in] A combination of [MALLOC_TYPE](malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="a27d5-107">fora Um ponteiro para o endereço de uma `IHostMAlloc` instância fornecida pelo host.</span><span class="sxs-lookup"><span data-stu-id="a27d5-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a27d5-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="a27d5-108">Return Value</span></span>  
  
|<span data-ttu-id="a27d5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a27d5-109">HRESULT</span></span>|<span data-ttu-id="a27d5-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="a27d5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a27d5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a27d5-111">S_OK</span></span>|<span data-ttu-id="a27d5-112">`CreateMAlloc` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a27d5-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="a27d5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a27d5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a27d5-114">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="a27d5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a27d5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a27d5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a27d5-116">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="a27d5-116">The call timed out.</span></span>|  
|<span data-ttu-id="a27d5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a27d5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a27d5-118">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="a27d5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a27d5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a27d5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a27d5-120">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="a27d5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a27d5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a27d5-121">E_FAIL</span></span>|<span data-ttu-id="a27d5-122">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="a27d5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a27d5-123">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="a27d5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a27d5-124">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a27d5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a27d5-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a27d5-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a27d5-126">Não há memória física suficiente disponível para concluir a solicitação de alocação.</span><span class="sxs-lookup"><span data-stu-id="a27d5-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a27d5-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="a27d5-127">Remarks</span></span>  

 <span data-ttu-id="a27d5-128">`CreateMAlloc` Retorna um objeto que permite que o CLR faça solicitações de alocação por meio do host em vez de usar as funções padrão do Win32.</span><span class="sxs-lookup"><span data-stu-id="a27d5-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a27d5-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a27d5-129">Requirements</span></span>  

 <span data-ttu-id="a27d5-130">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a27d5-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a27d5-131">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a27d5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a27d5-132">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a27d5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a27d5-133">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a27d5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a27d5-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="a27d5-134">See also</span></span>

- [<span data-ttu-id="a27d5-135">Interface IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="a27d5-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="a27d5-136">Interface IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="a27d5-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
