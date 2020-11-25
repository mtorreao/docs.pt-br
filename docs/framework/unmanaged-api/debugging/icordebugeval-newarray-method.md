---
title: Método ICorDebugEval::NewArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: ef6cbe2cef3c52d9a4b47ff77e8aeb5159e89c76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729753"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="9912f-102">Método ICorDebugEval::NewArray</span><span class="sxs-lookup"><span data-stu-id="9912f-102">ICorDebugEval::NewArray Method</span></span>

<span data-ttu-id="9912f-103">Aloca uma nova matriz do tipo e das dimensões do elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="9912f-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="9912f-104">Esse método é obsoleto no .NET Framework versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="9912f-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9912f-105">Use [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="9912f-105">Use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9912f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9912f-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9912f-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9912f-107">Parameters</span></span>  

 `elementType`  
 <span data-ttu-id="9912f-108">no Um valor da enumeração CorElementType que especifica o tipo de elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="9912f-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="9912f-109">no Um ponteiro para um objeto ICorDebugClass que especifica a classe do elemento.</span><span class="sxs-lookup"><span data-stu-id="9912f-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="9912f-110">Esse valor pode ser nulo se o tipo de elemento for um tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="9912f-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="9912f-111">no O número de dimensões da matriz.</span><span class="sxs-lookup"><span data-stu-id="9912f-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="9912f-112">No .NET Framework 2,0, esse valor deve ser 1.</span><span class="sxs-lookup"><span data-stu-id="9912f-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="9912f-113">no O tamanho, em bytes, de cada dimensão da matriz.</span><span class="sxs-lookup"><span data-stu-id="9912f-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="9912f-114">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="9912f-114">[in] Optional.</span></span> <span data-ttu-id="9912f-115">O limite inferior de cada dimensão da matriz.</span><span class="sxs-lookup"><span data-stu-id="9912f-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="9912f-116">Se esse valor for omitido, um limite inferior de zero será assumido para cada dimensão.</span><span class="sxs-lookup"><span data-stu-id="9912f-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9912f-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="9912f-117">Remarks</span></span>  

 <span data-ttu-id="9912f-118">A matriz é sempre criada no domínio do aplicativo no qual o thread está sendo executado no momento.</span><span class="sxs-lookup"><span data-stu-id="9912f-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9912f-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9912f-119">Requirements</span></span>  

 <span data-ttu-id="9912f-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9912f-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9912f-121">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9912f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9912f-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9912f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9912f-123">**Versões do .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="9912f-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
