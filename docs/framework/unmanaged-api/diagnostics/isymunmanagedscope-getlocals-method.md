---
title: Método ISymUnmanagedScope::GetLocals
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: 3a2045466340f92dd8421090c74a442068e8bfaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731404"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="6ea17-102">Método ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="6ea17-102">ISymUnmanagedScope::GetLocals Method</span></span>

<span data-ttu-id="6ea17-103">Obtém as variáveis locais definidas nesse escopo.</span><span class="sxs-lookup"><span data-stu-id="6ea17-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea17-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6ea17-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea17-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6ea17-105">Parameters</span></span>  

 `cLocals`  
 <span data-ttu-id="6ea17-106">no Um `ULONG32` que indica o tamanho da `locals` matriz.</span><span class="sxs-lookup"><span data-stu-id="6ea17-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="6ea17-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho do buffer necessário para conter as variáveis locais.</span><span class="sxs-lookup"><span data-stu-id="6ea17-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="6ea17-108">fora A matriz que recebe as variáveis locais.</span><span class="sxs-lookup"><span data-stu-id="6ea17-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ea17-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="6ea17-109">Return Value</span></span>  

 <span data-ttu-id="6ea17-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="6ea17-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea17-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ea17-111">Requirements</span></span>  

 <span data-ttu-id="6ea17-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6ea17-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea17-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="6ea17-113">See also</span></span>

- [<span data-ttu-id="6ea17-114">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="6ea17-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
