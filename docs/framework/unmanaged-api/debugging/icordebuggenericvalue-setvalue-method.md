---
title: Método ICorDebugGenericValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
ms.openlocfilehash: 493793c45e7d13511e4c36fe76e472a856b50d72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705729"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="0e2f8-102">Método ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="0e2f8-102">ICorDebugGenericValue::SetValue Method</span></span>

<span data-ttu-id="0e2f8-103">Copia um novo valor do buffer especificado.</span><span class="sxs-lookup"><span data-stu-id="0e2f8-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e2f8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0e2f8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e2f8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0e2f8-105">Parameters</span></span>  

 `pFrom`  
 <span data-ttu-id="0e2f8-106">no Um ponteiro para o buffer do qual copiar o valor.</span><span class="sxs-lookup"><span data-stu-id="0e2f8-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e2f8-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="0e2f8-107">Remarks</span></span>  

 <span data-ttu-id="0e2f8-108">Para tipos de referência, o valor é a referência, não o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0e2f8-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e2f8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e2f8-109">Requirements</span></span>  

 <span data-ttu-id="0e2f8-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e2f8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e2f8-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e2f8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e2f8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e2f8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e2f8-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e2f8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
