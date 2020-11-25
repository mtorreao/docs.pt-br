---
title: Método ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: e55c53b9610dcadee92ba9871bf52e3dacb5796b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726230"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="1c73b-102">Método ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="1c73b-102">ICorDebugGCReferenceEnum::Next Method</span></span>

<span data-ttu-id="1c73b-103">Obtém o número especificado de instâncias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contêm informações sobre objetos que serão coletados como lixo.</span><span class="sxs-lookup"><span data-stu-id="1c73b-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c73b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c73b-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c73b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1c73b-105">Parameters</span></span>  

 <span data-ttu-id="1c73b-106">celt</span><span class="sxs-lookup"><span data-stu-id="1c73b-106">celt</span></span>  
 <span data-ttu-id="1c73b-107">no O número de raízes a serem recuperadas.</span><span class="sxs-lookup"><span data-stu-id="1c73b-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="1c73b-108">raiz</span><span class="sxs-lookup"><span data-stu-id="1c73b-108">roots</span></span>  
 <span data-ttu-id="1c73b-109">fora Uma matriz de ponteiros, cada um dos quais aponta para um objeto [COR_GC_REFERENCE](cor-gc-reference-structure.md) que representa a raiz de um objeto a ser coletado pelo lixo.</span><span class="sxs-lookup"><span data-stu-id="1c73b-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="1c73b-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="1c73b-110">pceltFetched</span></span>  
 <span data-ttu-id="1c73b-111">fora Um ponteiro para o número de objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) realmente retornados em `roots` .</span><span class="sxs-lookup"><span data-stu-id="1c73b-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="1c73b-112">Esse valor pode ser `null` se `celt` for 1.</span><span class="sxs-lookup"><span data-stu-id="1c73b-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c73b-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="1c73b-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c73b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c73b-114">Requirements</span></span>  

 <span data-ttu-id="1c73b-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c73b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c73b-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c73b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c73b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c73b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c73b-118">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c73b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c73b-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="1c73b-119">See also</span></span>

- [<span data-ttu-id="1c73b-120">Interface ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="1c73b-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="1c73b-121">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="1c73b-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
