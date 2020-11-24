---
title: Interface ICorDebugThread2
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: fd4ad536d7d3df2b8f91f206459122cf083c8b9c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691130"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="fd797-102">Interface ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="fd797-102">ICorDebugThread2 Interface</span></span>

<span data-ttu-id="fd797-103">Serve como uma extensão lógica para a interface ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="fd797-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd797-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fd797-104">Methods</span></span>  
  
|<span data-ttu-id="fd797-105">Método</span><span class="sxs-lookup"><span data-stu-id="fd797-105">Method</span></span>|<span data-ttu-id="fd797-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="fd797-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd797-107">Método GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="fd797-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="fd797-108">Obtém uma matriz de instâncias de COR_ACTIVE_FUNCTION que contêm dados sobre as funções ativas nos quadros de um thread.</span><span class="sxs-lookup"><span data-stu-id="fd797-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="fd797-109">Método GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="fd797-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="fd797-110">Obtém um identificador de conexão para isso `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="fd797-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="fd797-111">Método GetTaskID</span><span class="sxs-lookup"><span data-stu-id="fd797-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="fd797-112">Obtém um identificador de tarefa para isso `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="fd797-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="fd797-113">Método GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="fd797-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="fd797-114">Obtém o identificador de thread do sistema operacional para isso `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="fd797-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="fd797-115">Método InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="fd797-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="fd797-116">Permite que um depurador intercepte a exceção atual em um thread.</span><span class="sxs-lookup"><span data-stu-id="fd797-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd797-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="fd797-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd797-118">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="fd797-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd797-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd797-119">Requirements</span></span>  

 <span data-ttu-id="fd797-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd797-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd797-121">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd797-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd797-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd797-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd797-123">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd797-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd797-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="fd797-124">See also</span></span>

- [<span data-ttu-id="fd797-125">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="fd797-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
