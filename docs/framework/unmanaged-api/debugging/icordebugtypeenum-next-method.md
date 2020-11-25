---
title: Método ICorDebugTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: 78ea76033b0b83c84446e16fb330bd3ba34c6e21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725697"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="e42cd-102">Método ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e42cd-102">ICorDebugTypeEnum::Next Method</span></span>

<span data-ttu-id="e42cd-103">Obtém o número de instâncias "ICorDebugType" especificadas pelo `celt` da enumeração, começando na posição atual.</span><span class="sxs-lookup"><span data-stu-id="e42cd-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e42cd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e42cd-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e42cd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e42cd-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="e42cd-106">no O número de `ICorDebugType` instâncias a serem recuperadas.</span><span class="sxs-lookup"><span data-stu-id="e42cd-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="e42cd-107">fora Uma matriz de ponteiros, cada um dos quais aponta para um `ICorDebugType` objeto.</span><span class="sxs-lookup"><span data-stu-id="e42cd-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e42cd-108">fora Aponta para o número de `ICorDebugType` instâncias realmente retornadas.</span><span class="sxs-lookup"><span data-stu-id="e42cd-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="e42cd-109">Esse valor pode ser nulo se `celt` for um.</span><span class="sxs-lookup"><span data-stu-id="e42cd-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e42cd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e42cd-110">Requirements</span></span>  

 <span data-ttu-id="e42cd-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e42cd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e42cd-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e42cd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e42cd-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e42cd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e42cd-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e42cd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e42cd-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="e42cd-115">See also</span></span>
