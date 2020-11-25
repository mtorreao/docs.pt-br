---
title: Método ICorDebugObjectValue2::GetVirtualMethodAndType
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
ms.openlocfilehash: 2a74688b90fbce63c9107d9389ddfd7bf5cd717b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695173"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="2e74a-102">Método ICorDebugObjectValue2::GetVirtualMethodAndType</span><span class="sxs-lookup"><span data-stu-id="2e74a-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>

<span data-ttu-id="2e74a-103">Este método ainda não foi implementado.</span><span class="sxs-lookup"><span data-stu-id="2e74a-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e74a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2e74a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="2e74a-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="2e74a-105">Remarks</span></span>  

 <span data-ttu-id="2e74a-106">Obtém ponteiros de interface para as instâncias "ICorDebugFunction" e "ICorDebugType" que representam o método e tipo mais derivados para a referência de membro especificada.</span><span class="sxs-lookup"><span data-stu-id="2e74a-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e74a-107">Confira também</span><span class="sxs-lookup"><span data-stu-id="2e74a-107">See also</span></span>
