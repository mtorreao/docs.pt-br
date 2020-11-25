---
title: Método ICorDebugValueBreakpoint::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
ms.openlocfilehash: 8b0ab22d4a782bb21e09d29c9121ef83782a4571
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722317"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="b0c2e-102">Método ICorDebugValueBreakpoint::GetValue</span><span class="sxs-lookup"><span data-stu-id="b0c2e-102">ICorDebugValueBreakpoint::GetValue Method</span></span>

<span data-ttu-id="b0c2e-103">Obtém um ponteiro de interface para um objeto "ICorDebugValue" que representa o valor do objeto no qual o ponto de interrupção está definido.</span><span class="sxs-lookup"><span data-stu-id="b0c2e-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c2e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b0c2e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0c2e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b0c2e-105">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="b0c2e-106">fora Um ponteiro para o endereço de um `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="b0c2e-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0c2e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0c2e-107">Requirements</span></span>  

 <span data-ttu-id="b0c2e-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0c2e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0c2e-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0c2e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0c2e-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0c2e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0c2e-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0c2e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c2e-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="b0c2e-112">See also</span></span>
