---
title: Método IDebuggerThreadControl::StartBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 1e0cb52a6b9f03209256e5398415b4ec632fb5e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705495"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="dc555-102">Método IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="dc555-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>

<span data-ttu-id="dc555-103">Notifica o host de que os serviços de depuração estão prestes a começar a bloquear todos os threads.</span><span class="sxs-lookup"><span data-stu-id="dc555-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc555-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dc555-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc555-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dc555-105">Parameters</span></span>  

 `dwUnused`  
 <span data-ttu-id="dc555-106">no Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="dc555-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc555-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="dc555-107">Remarks</span></span>  

 <span data-ttu-id="dc555-108">O `StartBlockingForDebugger` método pode ser chamado em um thread de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="dc555-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc555-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc555-109">Requirements</span></span>  

 <span data-ttu-id="dc555-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc555-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc555-111">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dc555-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc555-112">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc555-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc555-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc555-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc555-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="dc555-114">See also</span></span>

- [<span data-ttu-id="dc555-115">Interface IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="dc555-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
