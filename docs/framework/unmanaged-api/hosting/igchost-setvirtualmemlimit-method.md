---
title: Método IGCHost::SetVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 9898b760edbb149afcd6bf957a30d0a47287485b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687802"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="32920-102">Método IGCHost::SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="32920-102">IGCHost::SetVirtualMemLimit Method</span></span>

<span data-ttu-id="32920-103">Define o tamanho máximo da memória virtual do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="32920-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32920-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="32920-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32920-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="32920-105">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="32920-106">no O tamanho máximo, em megabytes, da memória virtual do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="32920-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32920-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="32920-107">Remarks</span></span>  

 <span data-ttu-id="32920-108">O tamanho máximo da memória virtual do tempo de execução pode ser alterado dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="32920-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32920-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32920-109">Requirements</span></span>  

 <span data-ttu-id="32920-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32920-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32920-111">**Cabeçalho:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="32920-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="32920-112">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32920-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32920-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32920-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32920-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="32920-114">See also</span></span>

- [<span data-ttu-id="32920-115">Interface IGCHost</span><span class="sxs-lookup"><span data-stu-id="32920-115">IGCHost Interface</span></span>](igchost-interface.md)
