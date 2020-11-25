---
title: Método IHostMemoryManager::ReleasedVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
ms.openlocfilehash: 8a875d59d270f087ce22079830818a9205309cc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731287"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="49466-102">Método IHostMemoryManager::ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="49466-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>

<span data-ttu-id="49466-103">Notifica o host que o Common Language Runtime (CLR) concluiu usando a memória especificada.</span><span class="sxs-lookup"><span data-stu-id="49466-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49466-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="49466-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49466-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="49466-105">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="49466-106">no Ponteiro para o endereço inicial da memória a ser liberada.</span><span class="sxs-lookup"><span data-stu-id="49466-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49466-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="49466-107">Remarks</span></span>  

 <span data-ttu-id="49466-108">O `ReleasedVirtualAddressSpace` método é um método de retorno de chamada e deve ser implementado pelo gravador do aplicativo de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="49466-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="49466-109">Ele é chamado pelo CLR.</span><span class="sxs-lookup"><span data-stu-id="49466-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49466-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49466-110">Requirements</span></span>  

 <span data-ttu-id="49466-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49466-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49466-112">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="49466-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49466-113">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49466-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49466-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49466-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49466-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="49466-115">See also</span></span>

- [<span data-ttu-id="49466-116">Interface IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="49466-116">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
