---
title: Interface ICorDebugHeapValue3
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: a1f4964c89aa3b658c57946d4b5a0327797118f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728700"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="2c438-102">Interface ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="2c438-102">ICorDebugHeapValue3 Interface</span></span>

<span data-ttu-id="2c438-103">Expõe as propriedades de bloqueio de monitoramento de objetos.</span><span class="sxs-lookup"><span data-stu-id="2c438-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="2c438-104">Essa interface estende as interfaces ICorDebugHeapValue e ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="2c438-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c438-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2c438-105">Methods</span></span>  
  
|<span data-ttu-id="2c438-106">Método</span><span class="sxs-lookup"><span data-stu-id="2c438-106">Method</span></span>|<span data-ttu-id="2c438-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2c438-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c438-108">Método GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="2c438-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="2c438-109">Retorna o thread gerenciado que possui o bloqueio de monitor neste objeto.</span><span class="sxs-lookup"><span data-stu-id="2c438-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="2c438-110">Método GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="2c438-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="2c438-111">Fornece uma lista ordenada de threads que são enfileirados no evento que está associado a um bloqueio de monitor.</span><span class="sxs-lookup"><span data-stu-id="2c438-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c438-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="2c438-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c438-113">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="2c438-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c438-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c438-114">Requirements</span></span>  

 <span data-ttu-id="2c438-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c438-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c438-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c438-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c438-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c438-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c438-118">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c438-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c438-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c438-119">See also</span></span>

- [<span data-ttu-id="2c438-120">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="2c438-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2c438-121">Depuração</span><span class="sxs-lookup"><span data-stu-id="2c438-121">Debugging</span></span>](index.md)
