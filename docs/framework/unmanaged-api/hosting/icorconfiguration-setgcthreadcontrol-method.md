---
title: Método ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 28b012bbe3f8c11ecd0afb8b5905336bd99c349c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724020"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="34f4c-102">Método ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="34f4c-102">ICorConfiguration::SetGCThreadControl Method</span></span>

<span data-ttu-id="34f4c-103">Define a interface de retorno de chamada para o agendamento de threads para tarefas sem tempo de execução que, de outra forma, seriam bloqueadas para uma coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="34f4c-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f4c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="34f4c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34f4c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="34f4c-105">Parameters</span></span>  

 `pGCThreadControl`  
 <span data-ttu-id="34f4c-106">no Um ponteiro para um objeto [IGCThreadControl](igcthreadcontrol-interface.md) que notifica o host sobre a suspensão de threads para tarefas sem tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="34f4c-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34f4c-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="34f4c-107">Remarks</span></span>  

 <span data-ttu-id="34f4c-108">O host pode escolher entre o retorno de chamada [IGCThreadControl:: ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) se deve reagendar um thread.</span><span class="sxs-lookup"><span data-stu-id="34f4c-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f4c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34f4c-109">Requirements</span></span>  

 <span data-ttu-id="34f4c-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34f4c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34f4c-111">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="34f4c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34f4c-112">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34f4c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34f4c-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34f4c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f4c-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="34f4c-114">See also</span></span>

- [<span data-ttu-id="34f4c-115">Interface ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="34f4c-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
