---
title: Método ISymUnmanagedScope::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
ms.openlocfilehash: 026ba35044bc7573dc54617dcade9cf3918a76ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725918"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="f8b69-102">Método ISymUnmanagedScope::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="f8b69-102">ISymUnmanagedScope::GetNamespaces Method</span></span>

<span data-ttu-id="f8b69-103">Obtém os namespaces que estão sendo usados nesse escopo.</span><span class="sxs-lookup"><span data-stu-id="f8b69-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8b69-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f8b69-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8b69-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f8b69-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="f8b69-106">no O tamanho da `namespaces` matriz.</span><span class="sxs-lookup"><span data-stu-id="f8b69-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="f8b69-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho do buffer necessário para conter os namespaces.</span><span class="sxs-lookup"><span data-stu-id="f8b69-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="f8b69-108">fora A matriz que recebe os namespaces.</span><span class="sxs-lookup"><span data-stu-id="f8b69-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8b69-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f8b69-109">Return Value</span></span>  

 <span data-ttu-id="f8b69-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="f8b69-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8b69-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8b69-111">Requirements</span></span>  

 <span data-ttu-id="f8b69-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f8b69-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b69-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="f8b69-113">See also</span></span>

- [<span data-ttu-id="f8b69-114">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="f8b69-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
