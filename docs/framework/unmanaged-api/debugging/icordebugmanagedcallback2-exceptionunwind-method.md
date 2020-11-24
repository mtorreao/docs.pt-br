---
title: Método ICorDebugManagedCallback2::ExceptionUnwind
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
ms.openlocfilehash: a15391b63012fec3d0e6a0aa67540c3d2541944c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671311"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="bef0d-102">Método ICorDebugManagedCallback2::ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="bef0d-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>

<span data-ttu-id="bef0d-103">Fornece uma notificação de status durante o processo de desenrolamento de exceções.</span><span class="sxs-lookup"><span data-stu-id="bef0d-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bef0d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bef0d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bef0d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bef0d-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="bef0d-106">no Um ponteiro para um objeto ICorDebugAppDomain que representa o domínio do aplicativo que contém o thread no qual a exceção foi gerada.</span><span class="sxs-lookup"><span data-stu-id="bef0d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="bef0d-107">no Um ponteiro para um objeto ICorDebugThread que representa o thread no qual a exceção foi gerada.</span><span class="sxs-lookup"><span data-stu-id="bef0d-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="bef0d-108">no Um valor da enumeração CorDebugExceptionUnwindCallbackType que especifica o evento que está sendo sinalizado pelo retorno de chamada durante a fase de desenrolamento.</span><span class="sxs-lookup"><span data-stu-id="bef0d-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bef0d-109">no Um valor da enumeração [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) que especifica informações adicionais sobre a exceção.</span><span class="sxs-lookup"><span data-stu-id="bef0d-109">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bef0d-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="bef0d-110">Remarks</span></span>  

 <span data-ttu-id="bef0d-111">`ExceptionUnwind` é chamado em vários pontos durante a fase de desenrolamento do processo de tratamento de exceção.</span><span class="sxs-lookup"><span data-stu-id="bef0d-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="bef0d-112">`ExceptionUnwind` pode ser chamado mais de uma vez ao desenrolar uma única exceção.</span><span class="sxs-lookup"><span data-stu-id="bef0d-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="bef0d-113">Se `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, o ponteiro de instrução estará no quadro folha do thread, no ponto de sequência antes (isso pode ser várias instruções antes) a instrução que levou à exceção.</span><span class="sxs-lookup"><span data-stu-id="bef0d-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bef0d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bef0d-114">Requirements</span></span>  

 <span data-ttu-id="bef0d-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bef0d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bef0d-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bef0d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bef0d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bef0d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bef0d-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bef0d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef0d-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="bef0d-119">See also</span></span>

- [<span data-ttu-id="bef0d-120">Interface ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="bef0d-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="bef0d-121">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="bef0d-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
