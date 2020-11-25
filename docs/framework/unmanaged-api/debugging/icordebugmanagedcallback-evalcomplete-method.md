---
title: Método ICorDebugManagedCallback::EvalComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
ms.openlocfilehash: e95874447528989af68f5c97825691532195889f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731794"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="417d7-102">Método ICorDebugManagedCallback::EvalComplete</span><span class="sxs-lookup"><span data-stu-id="417d7-102">ICorDebugManagedCallback::EvalComplete Method</span></span>

<span data-ttu-id="417d7-103">Notifica o depurador de que uma avaliação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="417d7-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417d7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="417d7-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="417d7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="417d7-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="417d7-106">no Um ponteiro para um objeto ICorDebugAppDomain que representa o domínio do aplicativo no qual a avaliação foi executada.</span><span class="sxs-lookup"><span data-stu-id="417d7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="417d7-107">no Um ponteiro para um objeto ICorDebugThread que representa o thread no qual a avaliação foi executada.</span><span class="sxs-lookup"><span data-stu-id="417d7-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="417d7-108">no Um ponteiro para um objeto ICorDebugEval que representa o código que realizou a avaliação.</span><span class="sxs-lookup"><span data-stu-id="417d7-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="417d7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="417d7-109">Requirements</span></span>  

 <span data-ttu-id="417d7-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="417d7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="417d7-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="417d7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="417d7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="417d7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="417d7-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="417d7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="417d7-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="417d7-114">See also</span></span>

- [<span data-ttu-id="417d7-115">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="417d7-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
