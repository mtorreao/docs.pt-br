---
title: Método IHostMemoryManager::VirtualQuery
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
ms.openlocfilehash: 6e3cb5bcec831f143d45f733c9e2f977390aade6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731235"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="5947b-102">Método IHostMemoryManager::VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="5947b-102">IHostMemoryManager::VirtualQuery Method</span></span>

<span data-ttu-id="5947b-103">Serve como um wrapper lógico para a função Win32 correspondente.</span><span class="sxs-lookup"><span data-stu-id="5947b-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="5947b-104">A implementação do Win32 de `VirtualQuery` recupera informações sobre um intervalo de páginas no espaço de endereço virtual do processo de chamada.</span><span class="sxs-lookup"><span data-stu-id="5947b-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5947b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5947b-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5947b-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5947b-106">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="5947b-107">no Um ponteiro para o endereço na memória virtual a ser consultada.</span><span class="sxs-lookup"><span data-stu-id="5947b-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="5947b-108">fora Um ponteiro para uma estrutura que contém informações sobre a região de memória especificada.</span><span class="sxs-lookup"><span data-stu-id="5947b-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="5947b-109">no O tamanho, em bytes, do buffer que `lpBuffer` aponta para.</span><span class="sxs-lookup"><span data-stu-id="5947b-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="5947b-110">fora Um ponteiro para o número de bytes retornados pelo buffer de informações.</span><span class="sxs-lookup"><span data-stu-id="5947b-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5947b-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="5947b-111">Return Value</span></span>  
  
|<span data-ttu-id="5947b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5947b-112">HRESULT</span></span>|<span data-ttu-id="5947b-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5947b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5947b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5947b-114">S_OK</span></span>|<span data-ttu-id="5947b-115">`VirtualQuery` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="5947b-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="5947b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5947b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5947b-117">O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.</span><span class="sxs-lookup"><span data-stu-id="5947b-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5947b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5947b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5947b-119">A chamada atingiu o tempo limite.</span><span class="sxs-lookup"><span data-stu-id="5947b-119">The call timed out.</span></span>|  
|<span data-ttu-id="5947b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5947b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5947b-121">O chamador não possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="5947b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5947b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5947b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5947b-123">Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.</span><span class="sxs-lookup"><span data-stu-id="5947b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5947b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5947b-124">E_FAIL</span></span>|<span data-ttu-id="5947b-125">Ocorreu uma falha catastrófica desconhecida.</span><span class="sxs-lookup"><span data-stu-id="5947b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5947b-126">Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo.</span><span class="sxs-lookup"><span data-stu-id="5947b-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5947b-127">As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5947b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5947b-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="5947b-128">Remarks</span></span>  

 <span data-ttu-id="5947b-129">`VirtualQuery` fornece informações sobre um intervalo de páginas no espaço de endereço virtual do processo de chamada.</span><span class="sxs-lookup"><span data-stu-id="5947b-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="5947b-130">Essa implementação define o valor do `pResult` parâmetro como o número de bytes retornados no buffer de informações e retorna um valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5947b-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="5947b-131">Na função do Win32 `VirtualQuery` , o valor de retorno é o tamanho do buffer.</span><span class="sxs-lookup"><span data-stu-id="5947b-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="5947b-132">Para obter mais informações, consulte a documentação da plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="5947b-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5947b-133">A implementação do sistema operacional do não `VirtualQuery` incorre em deadlock e pode ser executada até a conclusão com threads aleatórios suspensos no código do usuário.</span><span class="sxs-lookup"><span data-stu-id="5947b-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="5947b-134">Tenha muito cuidado ao implementar uma versão hospedada desse método.</span><span class="sxs-lookup"><span data-stu-id="5947b-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5947b-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5947b-135">Requirements</span></span>  

 <span data-ttu-id="5947b-136">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5947b-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5947b-137">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5947b-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5947b-138">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5947b-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5947b-139">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5947b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5947b-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="5947b-140">See also</span></span>

- [<span data-ttu-id="5947b-141">Interface IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="5947b-141">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
