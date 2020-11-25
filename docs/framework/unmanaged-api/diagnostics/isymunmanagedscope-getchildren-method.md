---
title: Método ISymUnmanagedScope::GetChildren
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
ms.openlocfilehash: 8f3c83a7a89553ba600f3e0e368eec0ddd0350e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727602"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="13c9f-102">Método ISymUnmanagedScope::GetChildren</span><span class="sxs-lookup"><span data-stu-id="13c9f-102">ISymUnmanagedScope::GetChildren Method</span></span>

<span data-ttu-id="13c9f-103">Obtém os filhos deste escopo.</span><span class="sxs-lookup"><span data-stu-id="13c9f-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c9f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="13c9f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13c9f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="13c9f-105">Parameters</span></span>  

 `cChildren`  
 <span data-ttu-id="13c9f-106">no Um `ULONG32` que indica o tamanho da `children` matriz.</span><span class="sxs-lookup"><span data-stu-id="13c9f-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="13c9f-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho do buffer necessário para conter os filhos.</span><span class="sxs-lookup"><span data-stu-id="13c9f-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="13c9f-108">fora A matriz de filhos retornada.</span><span class="sxs-lookup"><span data-stu-id="13c9f-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13c9f-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="13c9f-109">Return Value</span></span>  

 <span data-ttu-id="13c9f-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="13c9f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13c9f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13c9f-111">Requirements</span></span>  

 <span data-ttu-id="13c9f-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="13c9f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c9f-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="13c9f-113">See also</span></span>

- [<span data-ttu-id="13c9f-114">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="13c9f-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="13c9f-115">Método GetParent</span><span class="sxs-lookup"><span data-stu-id="13c9f-115">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
