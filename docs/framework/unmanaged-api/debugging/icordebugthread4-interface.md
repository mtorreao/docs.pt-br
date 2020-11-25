---
title: Interface ICorDebugThread4
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
ms.openlocfilehash: 5c108420772be9e6d0932f3759f18da9446f99d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727933"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="5da98-102">Interface ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="5da98-102">ICorDebugThread4 Interface</span></span>

<span data-ttu-id="5da98-103">Fornece informações de bloqueio de thread.</span><span class="sxs-lookup"><span data-stu-id="5da98-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5da98-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5da98-104">Methods</span></span>  
  
|<span data-ttu-id="5da98-105">Método</span><span class="sxs-lookup"><span data-stu-id="5da98-105">Method</span></span>|<span data-ttu-id="5da98-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="5da98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5da98-107">Método GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="5da98-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="5da98-108">Fornece uma enumeração ordenada de estruturas [CorDebugBlockingObject](cordebugblockingobject-structure.md) que fornecem informações de bloqueio de thread.</span><span class="sxs-lookup"><span data-stu-id="5da98-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="5da98-109">Método HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="5da98-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="5da98-110">Indica se o thread já teve uma exceção sem tratamento.</span><span class="sxs-lookup"><span data-stu-id="5da98-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="5da98-111">Método GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="5da98-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="5da98-112">Obtém o objeto [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) atual no thread atual.</span><span class="sxs-lookup"><span data-stu-id="5da98-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5da98-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="5da98-113">Remarks</span></span>  

 <span data-ttu-id="5da98-114">Essa interface é uma extensão lógica das interfaces ICorDebugThread, ICorDebugThread2 e [ICorDebugThread3](icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5da98-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5da98-115">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="5da98-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5da98-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5da98-116">Requirements</span></span>  

 <span data-ttu-id="5da98-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5da98-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5da98-118">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5da98-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5da98-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5da98-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5da98-120">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5da98-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da98-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="5da98-121">See also</span></span>

- [<span data-ttu-id="5da98-122">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="5da98-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5da98-123">Depuração</span><span class="sxs-lookup"><span data-stu-id="5da98-123">Debugging</span></span>](index.md)
