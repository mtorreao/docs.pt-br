---
title: Método ICorDebugObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: 8e188f304908a8029a57bb059046205c35346f3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724683"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="29c7e-102">Método ICorDebugObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="29c7e-102">ICorDebugObjectEnum::Next Method</span></span>

<span data-ttu-id="29c7e-103">Obtém os endereços virtuais relativos (RVAs) do número especificado de objetos da enumeração, começando na posição atual.</span><span class="sxs-lookup"><span data-stu-id="29c7e-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c7e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="29c7e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29c7e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="29c7e-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="29c7e-106">no O número de objetos a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="29c7e-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="29c7e-107">fora Uma matriz de ponteiros, cada um dos quais aponta para um objeto CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="29c7e-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="29c7e-108">fora Aponta para o número de objetos realmente retornados.</span><span class="sxs-lookup"><span data-stu-id="29c7e-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="29c7e-109">Esse valor pode ser nulo se `celt` for um.</span><span class="sxs-lookup"><span data-stu-id="29c7e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29c7e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29c7e-110">Requirements</span></span>  

 <span data-ttu-id="29c7e-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c7e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c7e-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29c7e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29c7e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29c7e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29c7e-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c7e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c7e-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="29c7e-115">See also</span></span>
