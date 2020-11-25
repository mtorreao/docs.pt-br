---
title: Método ISymUnmanagedVariable::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: 68d20c33c5ccd554554cae57ee55f6f51d5d980c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733302"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="03b34-102">Método ISymUnmanagedVariable::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="03b34-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>

<span data-ttu-id="03b34-103">Obtém o deslocamento inicial dessa variável dentro de seu pai.</span><span class="sxs-lookup"><span data-stu-id="03b34-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="03b34-104">Se essa for uma variável local dentro de um escopo, o deslocamento de início se enquadrará dentro dos deslocamentos definidos para o escopo.</span><span class="sxs-lookup"><span data-stu-id="03b34-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03b34-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="03b34-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03b34-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="03b34-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="03b34-107">fora Um ponteiro para um `ULONG32` que recebe o deslocamento de início.</span><span class="sxs-lookup"><span data-stu-id="03b34-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03b34-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="03b34-108">Return Value</span></span>  

 <span data-ttu-id="03b34-109">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="03b34-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03b34-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03b34-110">Requirements</span></span>  

 <span data-ttu-id="03b34-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="03b34-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b34-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="03b34-112">See also</span></span>

- [<span data-ttu-id="03b34-113">Interface ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="03b34-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="03b34-114">Método GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="03b34-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
