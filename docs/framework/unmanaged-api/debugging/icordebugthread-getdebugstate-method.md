---
title: Método ICorDebugThread::GetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
ms.openlocfilehash: 746fef3629e6573d7dfe47d5a3fcf9ee9a1d4250
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728037"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="15a1c-102">Método ICorDebugThread::GetDebugState</span><span class="sxs-lookup"><span data-stu-id="15a1c-102">ICorDebugThread::GetDebugState Method</span></span>

<span data-ttu-id="15a1c-103">Obtém o estado de depuração atual deste objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="15a1c-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a1c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="15a1c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15a1c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="15a1c-105">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="15a1c-106">fora Um ponteiro para uma combinação de bits de valor de enumeração CorDebugThreadState que descreve o estado de depuração atual desse thread.</span><span class="sxs-lookup"><span data-stu-id="15a1c-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15a1c-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="15a1c-107">Remarks</span></span>  

 <span data-ttu-id="15a1c-108">Se o processo estiver parado no momento, `pState` representará o estado de depuração que existiria para esse thread se o processo fosse continuado, não o estado real atual desse thread.</span><span class="sxs-lookup"><span data-stu-id="15a1c-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a1c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15a1c-109">Requirements</span></span>  

 <span data-ttu-id="15a1c-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15a1c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a1c-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15a1c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15a1c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15a1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15a1c-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a1c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
