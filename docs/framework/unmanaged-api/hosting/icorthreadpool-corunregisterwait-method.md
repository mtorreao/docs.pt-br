---
title: Método ICorThreadpool::CorUnregisterWait
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
ms.openlocfilehash: 38b3655da75750ffc3ea1c7983ce3b549d76f087
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733965"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="32f97-102">Método ICorThreadpool::CorUnregisterWait</span><span class="sxs-lookup"><span data-stu-id="32f97-102">ICorThreadpool::CorUnregisterWait Method</span></span>

<span data-ttu-id="32f97-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="32f97-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32f97-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="32f97-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="32f97-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32f97-105">Requirements</span></span>  

 <span data-ttu-id="32f97-106">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32f97-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32f97-107">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="32f97-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32f97-108">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32f97-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32f97-109">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32f97-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f97-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="32f97-110">See also</span></span>

- [<span data-ttu-id="32f97-111">Interface ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="32f97-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
