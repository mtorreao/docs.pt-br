---
title: Método ICorDebugExceptionObjectCallStackEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
ms.openlocfilehash: 17d5367564ec1ec98efc264ad9a5794c0d04a947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672130"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="b7f44-102">Método ICorDebugExceptionObjectCallStackEnum::Next</span><span class="sxs-lookup"><span data-stu-id="b7f44-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>

<span data-ttu-id="b7f44-103">Obtém o número especificado de instâncias [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) que contêm informações de uma pilha de chamadas do objeto de exceção.</span><span class="sxs-lookup"><span data-stu-id="b7f44-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7f44-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b7f44-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7f44-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b7f44-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="b7f44-106">no O número de instâncias de [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) a serem recuperadas.</span><span class="sxs-lookup"><span data-stu-id="b7f44-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="b7f44-107">fora Uma matriz de ponteiros, cada um dos quais aponta para um objeto [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="b7f44-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b7f44-108">fora Um ponteiro para o número de instâncias de [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) retornadas na verdade.</span><span class="sxs-lookup"><span data-stu-id="b7f44-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7f44-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="b7f44-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7f44-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7f44-110">Requirements</span></span>  

 <span data-ttu-id="b7f44-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7f44-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7f44-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7f44-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7f44-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7f44-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7f44-114">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7f44-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f44-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="b7f44-115">See also</span></span>

- [<span data-ttu-id="b7f44-116">Interface ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="b7f44-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="b7f44-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="b7f44-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
