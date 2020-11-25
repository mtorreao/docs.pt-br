---
title: Interface ICorDebugArrayValue
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: 90688132b98f8316a4b08988c08b2f7cc7ce0fd8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725037"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="3189b-102">Interface ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="3189b-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="3189b-103">Uma subclasse de ICorDebugHeapValue que representa uma matriz unidimensional ou multidimensional.</span><span class="sxs-lookup"><span data-stu-id="3189b-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3189b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3189b-104">Methods</span></span>  
  
|<span data-ttu-id="3189b-105">Método</span><span class="sxs-lookup"><span data-stu-id="3189b-105">Method</span></span>|<span data-ttu-id="3189b-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="3189b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3189b-107">Método GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="3189b-107">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="3189b-108">Obtém o índice base de cada dimensão na matriz.</span><span class="sxs-lookup"><span data-stu-id="3189b-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="3189b-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="3189b-109">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="3189b-110">Obtém o número total de elementos na matriz.</span><span class="sxs-lookup"><span data-stu-id="3189b-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="3189b-111">Método GetDimensions</span><span class="sxs-lookup"><span data-stu-id="3189b-111">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="3189b-112">Obtém as dimensões da matriz.</span><span class="sxs-lookup"><span data-stu-id="3189b-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="3189b-113">Método GetElement</span><span class="sxs-lookup"><span data-stu-id="3189b-113">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="3189b-114">Obtém um valor que representa o elemento fornecido na matriz.</span><span class="sxs-lookup"><span data-stu-id="3189b-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="3189b-115">Método GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="3189b-115">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="3189b-116">Obtém o elemento na posição fornecida, tratando a matriz como uma matriz unidimensional com base em zero.</span><span class="sxs-lookup"><span data-stu-id="3189b-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="3189b-117">Método GetElementType</span><span class="sxs-lookup"><span data-stu-id="3189b-117">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="3189b-118">Obtém o tipo simples dos elementos na matriz.</span><span class="sxs-lookup"><span data-stu-id="3189b-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="3189b-119">Método GetRank</span><span class="sxs-lookup"><span data-stu-id="3189b-119">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="3189b-120">Obtém o número de dimensões na matriz.</span><span class="sxs-lookup"><span data-stu-id="3189b-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="3189b-121">Método HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="3189b-121">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="3189b-122">Determina se a matriz tem índices base.</span><span class="sxs-lookup"><span data-stu-id="3189b-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3189b-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="3189b-123">Remarks</span></span>  

 <span data-ttu-id="3189b-124">`ICorDebugArrayValue` dá suporte a matrizes unidimensionais e multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="3189b-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3189b-125">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="3189b-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3189b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3189b-126">Requirements</span></span>  

 <span data-ttu-id="3189b-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3189b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3189b-128">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3189b-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3189b-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3189b-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3189b-130">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3189b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3189b-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="3189b-131">See also</span></span>

- [<span data-ttu-id="3189b-132">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="3189b-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
