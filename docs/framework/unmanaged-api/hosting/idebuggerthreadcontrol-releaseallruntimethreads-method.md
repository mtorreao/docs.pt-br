---
title: Método IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: 490648ab8883b1dba257b82c0d0fa3c8e4783814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684155"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="0b845-102">Método IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="0b845-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>

<span data-ttu-id="0b845-103">Notifica o host de que os serviços de depuração estão prestes a liberar todos os threads bloqueados.</span><span class="sxs-lookup"><span data-stu-id="0b845-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b845-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0b845-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="0b845-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="0b845-105">Remarks</span></span>  

 <span data-ttu-id="0b845-106">O `ReleaseAllRuntimeThreads` método nunca será chamado em um thread de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0b845-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="0b845-107">Se o host tiver um thread de tempo de execução bloqueado, ele deverá liberá-lo agora.</span><span class="sxs-lookup"><span data-stu-id="0b845-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b845-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b845-108">Requirements</span></span>  

 <span data-ttu-id="0b845-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b845-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b845-110">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0b845-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b845-111">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b845-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b845-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b845-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b845-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="0b845-113">See also</span></span>

- [<span data-ttu-id="0b845-114">Interface IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="0b845-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
