---
title: Método ICorDebugController::EnumerateThreads
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: f98118f9206d9ccd7dc9dc9a943500c7b4cd676a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732652"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="26a37-102">Método ICorDebugController::EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="26a37-102">ICorDebugController::EnumerateThreads Method</span></span>

<span data-ttu-id="26a37-103">Obtém um enumerador para os threads gerenciados ativos no processo.</span><span class="sxs-lookup"><span data-stu-id="26a37-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a37-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="26a37-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26a37-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="26a37-105">Parameters</span></span>  

 `ppThreads`  
 <span data-ttu-id="26a37-106">fora Um ponteiro para o endereço de um objeto "ICorDebugThreadEnum" que representa um enumerador para todos os threads gerenciados que estão ativos no processo.</span><span class="sxs-lookup"><span data-stu-id="26a37-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26a37-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="26a37-107">Remarks</span></span>  

 <span data-ttu-id="26a37-108">Um thread é considerado ativo após o retorno de chamada [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) ter sido expedido e antes de o retorno de chamada [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) ser expedido.</span><span class="sxs-lookup"><span data-stu-id="26a37-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="26a37-109">Um thread gerenciado pode não ter necessariamente nenhum quadro gerenciado em sua pilha.</span><span class="sxs-lookup"><span data-stu-id="26a37-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="26a37-110">Os threads podem ser enumerados mesmo antes do retorno de chamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="26a37-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="26a37-111">A enumeração estará naturalmente vazia.</span><span class="sxs-lookup"><span data-stu-id="26a37-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a37-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26a37-112">Requirements</span></span>  

 <span data-ttu-id="26a37-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a37-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a37-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26a37-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26a37-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26a37-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26a37-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26a37-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a37-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="26a37-117">See also</span></span>
