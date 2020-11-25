---
title: Método ICorDebugArrayValue::GetElementAtPosition
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
ms.openlocfilehash: a6e5ecee9a89da98a73dfb20935c5ec594d5958f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732925"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="6e843-102">Método ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="6e843-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>

<span data-ttu-id="6e843-103">Obtém o elemento na posição fornecida, tratando a matriz como uma matriz unidimensional com base em zero.</span><span class="sxs-lookup"><span data-stu-id="6e843-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e843-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e843-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e843-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6e843-105">Parameters</span></span>  

 `nPosition`  
 <span data-ttu-id="6e843-106">no A posição do elemento a ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="6e843-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6e843-107">fora Um ponteiro para o endereço de um objeto ICorDebugValue que representa o valor do elemento.</span><span class="sxs-lookup"><span data-stu-id="6e843-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e843-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e843-108">Remarks</span></span>  

 <span data-ttu-id="6e843-109">O layout de uma matriz de várias dimensões segue o estilo C++ de layout de matriz.</span><span class="sxs-lookup"><span data-stu-id="6e843-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e843-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e843-110">Requirements</span></span>  

 <span data-ttu-id="6e843-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e843-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e843-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e843-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e843-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e843-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e843-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e843-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
