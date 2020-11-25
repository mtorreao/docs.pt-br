---
title: Método ICorDebugManagedCallback::EditAndContinueRemap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
ms.openlocfilehash: 1d8aa2cca9dbbeaa9e03813b177ca59125770803
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721277"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="3e999-102">Método ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="3e999-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>

<span data-ttu-id="3e999-103">Esse método foi substituído.</span><span class="sxs-lookup"><span data-stu-id="3e999-103">This method has been deprecated.</span></span> <span data-ttu-id="3e999-104">Ele notifica o depurador de que um evento de remapeamento foi enviado para o ambiente de desenvolvimento integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="3e999-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e999-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3e999-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="3e999-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="3e999-106">Remarks</span></span>  

 <span data-ttu-id="3e999-107">O `EditAndContinueRemap` método é chamado quando a execução do código em uma versão antiga de uma função atualizada foi tentada.</span><span class="sxs-lookup"><span data-stu-id="3e999-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="3e999-108">O Common Language Runtime chama o `EditAndContinueRemap` método para enviar um evento de remapeamento para o IDE.</span><span class="sxs-lookup"><span data-stu-id="3e999-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e999-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e999-109">Requirements</span></span>  

 <span data-ttu-id="3e999-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e999-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e999-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e999-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e999-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e999-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e999-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e999-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e999-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="3e999-114">See also</span></span>

- [<span data-ttu-id="3e999-115">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="3e999-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
