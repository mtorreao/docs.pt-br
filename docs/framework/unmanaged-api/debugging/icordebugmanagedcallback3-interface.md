---
title: Interface ICorDebugManagedCallback3
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
ms.openlocfilehash: e04f5be6d2612b26bf7d71807753d170e6a5a7a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723292"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="e17a7-102">Interface ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="e17a7-102">ICorDebugManagedCallback3 Interface</span></span>

<span data-ttu-id="e17a7-103">Fornece um método de retorno de chamada que indica que uma notificação personalizada ativada do depurador foi gerada.</span><span class="sxs-lookup"><span data-stu-id="e17a7-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e17a7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e17a7-104">Methods</span></span>  
  
|<span data-ttu-id="e17a7-105">Método</span><span class="sxs-lookup"><span data-stu-id="e17a7-105">Method</span></span>|<span data-ttu-id="e17a7-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e17a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e17a7-107">Método CustomNotification</span><span class="sxs-lookup"><span data-stu-id="e17a7-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="e17a7-108">Indica que uma notificação de depurador personalizada habilitada foi gerada.</span><span class="sxs-lookup"><span data-stu-id="e17a7-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e17a7-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="e17a7-109">Remarks</span></span>  

 <span data-ttu-id="e17a7-110">Essa interface é uma extensão lógica das interfaces [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) e [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e17a7-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e17a7-111">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="e17a7-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e17a7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e17a7-112">Requirements</span></span>  

 <span data-ttu-id="e17a7-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e17a7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e17a7-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e17a7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e17a7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e17a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e17a7-116">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e17a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e17a7-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="e17a7-117">See also</span></span>

- [<span data-ttu-id="e17a7-118">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e17a7-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="e17a7-119">Interface ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="e17a7-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e17a7-120">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="e17a7-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e17a7-121">Depuração</span><span class="sxs-lookup"><span data-stu-id="e17a7-121">Debugging</span></span>](index.md)
