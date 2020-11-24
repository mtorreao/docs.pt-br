---
title: Método ICorDebugThread2::GetActiveFunctions
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
ms.openlocfilehash: 2d5674d6b5962ca539de02cda1e5658daed83622
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678714"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="192e7-102">Método ICorDebugThread2::GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="192e7-102">ICorDebugThread2::GetActiveFunctions Method</span></span>

<span data-ttu-id="192e7-103">Obtém informações sobre a função ativa em cada um dos quadros deste thread.</span><span class="sxs-lookup"><span data-stu-id="192e7-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="192e7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="192e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="192e7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="192e7-105">Parameters</span></span>  

 `cFunctions`  
 <span data-ttu-id="192e7-106">no O tamanho da `pFunctions` matriz.</span><span class="sxs-lookup"><span data-stu-id="192e7-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="192e7-107">fora Um ponteiro para o número de objetos retornados na `pFunctions` matriz.</span><span class="sxs-lookup"><span data-stu-id="192e7-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="192e7-108">O número de objetos retornados será igual ao número de quadros gerenciados na pilha.</span><span class="sxs-lookup"><span data-stu-id="192e7-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="192e7-109">[entrada, saída] Uma matriz de objetos COR_ACTIVE_FUNCTION, cada um dos quais contém informações sobre as funções ativas nos quadros deste thread.</span><span class="sxs-lookup"><span data-stu-id="192e7-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="192e7-110">O primeiro elemento será usado para o quadro folha e assim por diante de volta para a raiz da pilha.</span><span class="sxs-lookup"><span data-stu-id="192e7-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="192e7-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="192e7-111">Remarks</span></span>  

 <span data-ttu-id="192e7-112">Se `pFunctions` for NULL na entrada, `GetActiveFunctions` retornará apenas o número de funções que estão na pilha.</span><span class="sxs-lookup"><span data-stu-id="192e7-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="192e7-113">Ou seja, se `pFunctions` for NULL na entrada, `GetActiveFunctions` retornará um valor somente no `pcFunctions` .</span><span class="sxs-lookup"><span data-stu-id="192e7-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="192e7-114">O `GetActiveFunctions` método é projetado como uma otimização sobre como obter as mesmas informações de quadros em um rastreamento de pilha e inclui apenas quadros que teriam um objeto ICorDebugILFrame para eles no rastreamento de pilha completo.</span><span class="sxs-lookup"><span data-stu-id="192e7-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="192e7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="192e7-115">Requirements</span></span>  

 <span data-ttu-id="192e7-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="192e7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="192e7-117">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="192e7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="192e7-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="192e7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="192e7-119">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="192e7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
