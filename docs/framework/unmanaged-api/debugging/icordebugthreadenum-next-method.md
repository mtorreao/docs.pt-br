---
title: Método ICorDebugThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: 226b386c7a38c9a0b28b3bcc0420d14f6f4f4e7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678409"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="a48dc-102">Método ICorDebugThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a48dc-102">ICorDebugThreadEnum::Next Method</span></span>

<span data-ttu-id="a48dc-103">Obtém o número de instâncias ICorDebugThread especificadas da enumeração, começando na posição atual.</span><span class="sxs-lookup"><span data-stu-id="a48dc-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a48dc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a48dc-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a48dc-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a48dc-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="a48dc-106">no O número de `ICorDebugThread` instâncias a serem recuperadas.</span><span class="sxs-lookup"><span data-stu-id="a48dc-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="a48dc-107">fora Uma matriz de ponteiros, cada um dos quais aponta para um `ICorDebugThread` objeto que representa um thread.</span><span class="sxs-lookup"><span data-stu-id="a48dc-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a48dc-108">fora Aponta para o número de `ICorDebugThread` instâncias realmente retornadas.</span><span class="sxs-lookup"><span data-stu-id="a48dc-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="a48dc-109">Esse valor pode ser nulo se `celt` for um.</span><span class="sxs-lookup"><span data-stu-id="a48dc-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a48dc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a48dc-110">Requirements</span></span>  

 <span data-ttu-id="a48dc-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a48dc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a48dc-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a48dc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a48dc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a48dc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a48dc-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a48dc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
