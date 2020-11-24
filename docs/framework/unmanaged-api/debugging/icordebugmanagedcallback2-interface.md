---
title: Interface ICorDebugManagedCallback2
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
ms.openlocfilehash: 937a2fb322eb63461d90e215635e1b10ab6afd09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689778"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="7b1df-102">Interface ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="7b1df-102">ICorDebugManagedCallback2 Interface</span></span>

<span data-ttu-id="7b1df-103">Fornece métodos para oferecer suporte à manipulação de exceção do depurador e aos assistentes de depuração gerenciados (MDAs).</span><span class="sxs-lookup"><span data-stu-id="7b1df-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="7b1df-104">`ICorDebugManagedCallback2` é uma extensão lógica da interface [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7b1df-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b1df-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7b1df-105">Methods</span></span>  
  
|<span data-ttu-id="7b1df-106">Método</span><span class="sxs-lookup"><span data-stu-id="7b1df-106">Method</span></span>|<span data-ttu-id="7b1df-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7b1df-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b1df-108">Método ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="7b1df-108">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="7b1df-109">Notifica o depurador de que o conjunto de tarefas associado à conexão especificada foi alterado.</span><span class="sxs-lookup"><span data-stu-id="7b1df-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="7b1df-110">Método CreateConnection</span><span class="sxs-lookup"><span data-stu-id="7b1df-110">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="7b1df-111">Notifica o depurador de que uma nova conexão foi criada.</span><span class="sxs-lookup"><span data-stu-id="7b1df-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="7b1df-112">Método DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="7b1df-112">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="7b1df-113">Notifica o depurador de que a conexão especificada foi encerrada.</span><span class="sxs-lookup"><span data-stu-id="7b1df-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="7b1df-114">Método Exception</span><span class="sxs-lookup"><span data-stu-id="7b1df-114">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="7b1df-115">Notifica o depurador de que uma pesquisa de um manipulador de exceção foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="7b1df-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="7b1df-116">Método ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="7b1df-116">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="7b1df-117">Fornece uma notificação de status durante o processo de desenrolamento de exceções.</span><span class="sxs-lookup"><span data-stu-id="7b1df-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="7b1df-118">Método FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="7b1df-118">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="7b1df-119">Notifica o depurador de que a execução de código mudou para uma nova versão de uma função editada.</span><span class="sxs-lookup"><span data-stu-id="7b1df-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="7b1df-120">Método FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="7b1df-120">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="7b1df-121">Notifica o depurador de que a execução de código atingiu um ponto de sequência em uma versão mais antiga de uma função editada.</span><span class="sxs-lookup"><span data-stu-id="7b1df-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="7b1df-122">Método MDANotification</span><span class="sxs-lookup"><span data-stu-id="7b1df-122">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="7b1df-123">Fornece uma notificação de que a execução de código encontrou uma mensagem do assistente de depuração gerenciada (MDA).</span><span class="sxs-lookup"><span data-stu-id="7b1df-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b1df-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="7b1df-124">Remarks</span></span>  

 <span data-ttu-id="7b1df-125">A `ICorDebugManagedCallback2` interface estende a `ICorDebugManagedCallback` interface para manipular novos eventos de depuração introduzidos na versão .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="7b1df-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="7b1df-126">Um depurador deve implementar `ICorDebugManagedCallback2` se estiver depurando .NET Framework aplicativos 2,0.</span><span class="sxs-lookup"><span data-stu-id="7b1df-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="7b1df-127">Uma instância do `ICorDebugManagedCallback` ou `ICorDebugManagedCallback2` é passada como o objeto de retorno de chamada para [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="7b1df-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b1df-128">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="7b1df-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b1df-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b1df-129">Requirements</span></span>  

 <span data-ttu-id="7b1df-130">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b1df-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b1df-131">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b1df-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b1df-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b1df-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b1df-133">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b1df-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b1df-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="7b1df-134">See also</span></span>

- [<span data-ttu-id="7b1df-135">Diagnosticando erros com assistentes de depuração gerenciados</span><span class="sxs-lookup"><span data-stu-id="7b1df-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7b1df-136">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="7b1df-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7b1df-137">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7b1df-137">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
