---
title: Método ICorDebugController::HasQueuedCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
ms.openlocfilehash: bd623f8bee2feafebe80c0c7513bcfb33d6ad367
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707887"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="d1036-102">Método ICorDebugController::HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="d1036-102">ICorDebugController::HasQueuedCallbacks Method</span></span>

<span data-ttu-id="d1036-103">Obtém um valor que indica se qualquer retorno de chamada gerenciado está na fila no momento para o thread especificado.</span><span class="sxs-lookup"><span data-stu-id="d1036-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1036-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d1036-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1036-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d1036-105">Parameters</span></span>  

 `pThread`  
 <span data-ttu-id="d1036-106">no Um ponteiro para um objeto "ICorDebugThread" que representa o thread.</span><span class="sxs-lookup"><span data-stu-id="d1036-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="d1036-107">fora Um ponteiro para um valor que ocorrerá `true` se qualquer retorno de chamada gerenciado estiver na fila no momento para o thread especificado; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="d1036-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d1036-108">Se NULL for especificado para o `pThread` parâmetro, `HasQueuedCallbacks` retornará `true` se houver retornos de chamada atualmente gerenciados em fila para qualquer thread.</span><span class="sxs-lookup"><span data-stu-id="d1036-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1036-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="d1036-109">Remarks</span></span>  

 <span data-ttu-id="d1036-110">Os retornos de chamada serão expedidos um de cada vez, sempre que [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) for chamado.</span><span class="sxs-lookup"><span data-stu-id="d1036-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="d1036-111">O depurador pode verificar esse sinalizador se desejar relatar vários eventos de depuração que ocorrem simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="d1036-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="d1036-112">Quando os eventos de depuração são enfileirados, eles já ocorreram, portanto, o depurador deve drenar toda a fila para ter certeza do estado do depurado.</span><span class="sxs-lookup"><span data-stu-id="d1036-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="d1036-113">(Chamada `ICorDebugController::Continue` para drenar a fila.) Por exemplo, se a fila contiver dois eventos de depuração no thread *x* e o depurador suspender o thread *x* após o primeiro evento de depuração e, em seguida `ICorDebugController::Continue` , chamar, o segundo evento de depuração para o thread *x* será expedido, embora o thread tenha sido suspenso.</span><span class="sxs-lookup"><span data-stu-id="d1036-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1036-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1036-114">Requirements</span></span>  

 <span data-ttu-id="d1036-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1036-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1036-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1036-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1036-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1036-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1036-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1036-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1036-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="d1036-119">See also</span></span>
