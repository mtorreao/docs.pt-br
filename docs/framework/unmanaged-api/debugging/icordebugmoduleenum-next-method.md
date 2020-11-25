---
title: Método ICorDebugModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: a4bdac42c584d5d34b072354de65ed20c6a80609
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709486"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="9ea71-102">Método ICorDebugModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="9ea71-102">ICorDebugModuleEnum::Next Method</span></span>

<span data-ttu-id="9ea71-103">Obtém o número de instâncias "ICorDebugModule" especificadas pelo `celt` da enumeração, começando na posição atual.</span><span class="sxs-lookup"><span data-stu-id="9ea71-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea71-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ea71-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ea71-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9ea71-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="9ea71-106">no O número de `ICorDebugModule` instâncias a serem recuperadas.</span><span class="sxs-lookup"><span data-stu-id="9ea71-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="9ea71-107">fora Uma matriz de ponteiros, cada um dos quais aponta para um `ICorDebugModule` objeto.</span><span class="sxs-lookup"><span data-stu-id="9ea71-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9ea71-108">fora Aponta para o número de `ICorDebugModule` instâncias realmente retornadas.</span><span class="sxs-lookup"><span data-stu-id="9ea71-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="9ea71-109">Esse valor pode ser nulo se `celt` for um.</span><span class="sxs-lookup"><span data-stu-id="9ea71-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea71-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ea71-110">Requirements</span></span>  

 <span data-ttu-id="9ea71-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ea71-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea71-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ea71-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ea71-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ea71-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ea71-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea71-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea71-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="9ea71-115">See also</span></span>
