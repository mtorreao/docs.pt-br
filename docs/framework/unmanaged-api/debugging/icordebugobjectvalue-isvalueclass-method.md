---
title: Método ICorDebugObjectValue::IsValueClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
ms.openlocfilehash: 7b637889986425767fd7e1166c73df3301075422
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695264"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="8d257-102">Método ICorDebugObjectValue::IsValueClass</span><span class="sxs-lookup"><span data-stu-id="8d257-102">ICorDebugObjectValue::IsValueClass Method</span></span>

<span data-ttu-id="8d257-103">Obtém um valor que indica se esse valor de objeto é um tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="8d257-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d257-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8d257-104">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d257-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8d257-105">Parameters</span></span>  

 `pbIsValueClass`  
 <span data-ttu-id="8d257-106">fora Um ponteiro para um valor booliano que é `true` se o valor do objeto, representado por esse "ICorDebugObjectValue", é um tipo de valor em vez de um tipo de referência; caso contrário, `pbIsValueClass` é `false` .</span><span class="sxs-lookup"><span data-stu-id="8d257-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d257-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d257-107">Requirements</span></span>  

 <span data-ttu-id="8d257-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d257-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d257-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d257-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d257-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d257-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d257-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d257-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d257-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="8d257-112">See also</span></span>
