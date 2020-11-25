---
title: Método ICorDebugValue::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 06f403f0b653866428a41240f99833ec1180eb86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731066"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="96e21-102">Método ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="96e21-102">ICorDebugValue::GetType Method</span></span>

<span data-ttu-id="96e21-103">Obtém o tipo primitivo desse objeto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="96e21-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96e21-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="96e21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96e21-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="96e21-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="96e21-106">fora Um ponteiro para um valor da enumeração "CorElementType" que indica o tipo do valor.</span><span class="sxs-lookup"><span data-stu-id="96e21-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96e21-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="96e21-107">Remarks</span></span>  

 <span data-ttu-id="96e21-108">Se o objeto for um tipo de tempo de execução complexo, esse tipo poderá ser examinado por meio das subclasses apropriadas da `ICorDebugValue` interface.</span><span class="sxs-lookup"><span data-stu-id="96e21-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="96e21-109">Por exemplo, "ICorDebugObjectValue", que herda de `ICorDebugValue` , representa um tipo complexo.</span><span class="sxs-lookup"><span data-stu-id="96e21-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="96e21-110">Os `GetType` métodos e [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) retornam informações sobre o tipo de um valor.</span><span class="sxs-lookup"><span data-stu-id="96e21-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="96e21-111">Eles são ambos substituídos pelo método [ICorDebugValue2:: Getexatotype](icordebugvalue2-getexacttype-method.md) com reconhecimento de genéricos.</span><span class="sxs-lookup"><span data-stu-id="96e21-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96e21-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96e21-112">Requirements</span></span>  

 <span data-ttu-id="96e21-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96e21-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96e21-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96e21-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96e21-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96e21-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96e21-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e21-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e21-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="96e21-117">See also</span></span>
