---
title: Método ICorConfiguration::SetDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
ms.openlocfilehash: 05df50d80c6b8962b3bdfe2708d5f9d30c58aaea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723916"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="4e784-102">Método ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="4e784-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>

<span data-ttu-id="4e784-103">Define a interface de retorno de chamada que os serviços de depuração chamarão à medida que os threads Common Language Runtime (CLR) são bloqueados e desbloqueados para depuração.</span><span class="sxs-lookup"><span data-stu-id="4e784-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e784-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4e784-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e784-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4e784-105">Parameters</span></span>  

 `pDebuggerThreadControl`  
 <span data-ttu-id="4e784-106">no Um ponteiro para um objeto [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) que notifica o host sobre o bloqueio e o desbloqueio de threads pelos serviços de depuração.</span><span class="sxs-lookup"><span data-stu-id="4e784-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e784-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e784-107">Requirements</span></span>  

 <span data-ttu-id="4e784-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e784-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e784-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e784-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e784-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e784-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e784-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e784-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e784-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="4e784-112">See also</span></span>

- [<span data-ttu-id="4e784-113">Interface ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4e784-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
