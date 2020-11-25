---
title: Método ISymUnmanagedVariable::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
ms.openlocfilehash: cf4179f839b62409d5b2185f3e11e8e732c29187
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721862"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="06658-102">Método ISymUnmanagedVariable::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="06658-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>

<span data-ttu-id="06658-103">Obtém o deslocamento final dessa variável dentro de seu pai.</span><span class="sxs-lookup"><span data-stu-id="06658-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="06658-104">Se essa for uma variável local dentro de um escopo, o deslocamento final se enquadrará dentro dos deslocamentos definidos para o escopo.</span><span class="sxs-lookup"><span data-stu-id="06658-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06658-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="06658-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06658-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="06658-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="06658-107">fora Um ponteiro para um `ULONG32` que recebe o deslocamento final.</span><span class="sxs-lookup"><span data-stu-id="06658-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06658-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="06658-108">Return Value</span></span>  

 <span data-ttu-id="06658-109">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="06658-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06658-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06658-110">Requirements</span></span>  

 <span data-ttu-id="06658-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="06658-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06658-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="06658-112">See also</span></span>

- [<span data-ttu-id="06658-113">Interface ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="06658-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="06658-114">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="06658-114">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)
