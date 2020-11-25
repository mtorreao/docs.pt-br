---
title: Método ICorDebugModuleBreakpoint::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
ms.openlocfilehash: b6363ef901d5297862ca46e685bb783aaaeb4123
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709590"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="2db64-102">Método ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="2db64-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>

<span data-ttu-id="2db64-103">Obtém um ponteiro de interface para um "ICorDebugModule" que faz referência ao módulo no qual esse ponto de interrupção está definido.</span><span class="sxs-lookup"><span data-stu-id="2db64-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db64-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2db64-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2db64-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2db64-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="2db64-106">fora Um ponteiro para o endereço de uma `ICorDebugModule` interface que faz referência ao módulo no qual o ponto de interrupção está definido.</span><span class="sxs-lookup"><span data-stu-id="2db64-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db64-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2db64-107">Requirements</span></span>  

 <span data-ttu-id="2db64-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2db64-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db64-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2db64-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2db64-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2db64-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2db64-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2db64-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db64-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="2db64-112">See also</span></span>
