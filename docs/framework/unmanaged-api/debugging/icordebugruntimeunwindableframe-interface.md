---
title: Interface ICorDebugRuntimeUnwindableFrame
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 6619b8888588341f23a93b83865cd2e75cc9b3db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712008"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="c4808-102">Interface ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="c4808-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>

<span data-ttu-id="c4808-103">Fornece suporte para os métodos não gerenciados que exigem que o CLR (Common Language Runtime) desenrole um quadro.</span><span class="sxs-lookup"><span data-stu-id="c4808-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4808-104">Comentários</span><span class="sxs-lookup"><span data-stu-id="c4808-104">Remarks</span></span>  

 <span data-ttu-id="c4808-105">`ICorDebugRuntimeUnwindableFrame` é uma versão especializada da interface ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="c4808-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="c4808-106">Ele é usado por métodos não gerenciados que exigem o tempo de execução para desenrolar um quadro na pilha atual.</span><span class="sxs-lookup"><span data-stu-id="c4808-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="c4808-107">As convenções de desenrolação existentes não funcionam, pois não usam código de compilação JIT.</span><span class="sxs-lookup"><span data-stu-id="c4808-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="c4808-108">Quando o depurador vê um quadro não-envento, ele deve usar o método [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) para desenrolar, mas deve executar a inspeção em si.</span><span class="sxs-lookup"><span data-stu-id="c4808-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="c4808-109">Quando o depurador recebe um `ICorDebugRuntimeUnwindableFrame` , ele pode chamar o método [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) para recuperar o contexto do quadro.</span><span class="sxs-lookup"><span data-stu-id="c4808-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4808-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4808-110">Requirements</span></span>  

 <span data-ttu-id="c4808-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4808-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4808-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4808-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4808-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4808-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4808-114">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4808-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4808-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="c4808-115">See also</span></span>

- [<span data-ttu-id="c4808-116">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="c4808-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c4808-117">Depuração</span><span class="sxs-lookup"><span data-stu-id="c4808-117">Debugging</span></span>](index.md)
