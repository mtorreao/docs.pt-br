---
title: Método ISymUnmanagedReader::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
ms.openlocfilehash: c90cd0d21eca6875d3dae32e4ca80cf42e6140b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720588"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="e2c3a-102">Método ISymUnmanagedReader::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="e2c3a-102">ISymUnmanagedReader::GetNamespaces Method</span></span>

<span data-ttu-id="e2c3a-103">Obtém os namespaces definidos no escopo global dentro deste armazenamento de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e2c3a-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c3a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e2c3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2c3a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e2c3a-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="e2c3a-106">no O tamanho da matriz de namespaces.</span><span class="sxs-lookup"><span data-stu-id="e2c3a-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="e2c3a-107">fora Um ponteiro para uma variável que recebe o comprimento da lista de namespace.</span><span class="sxs-lookup"><span data-stu-id="e2c3a-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="e2c3a-108">fora Um ponteiro para uma variável que recebe a lista de namespace.</span><span class="sxs-lookup"><span data-stu-id="e2c3a-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2c3a-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="e2c3a-109">Return Value</span></span>  

 <span data-ttu-id="e2c3a-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="e2c3a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2c3a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2c3a-111">Requirements</span></span>  

 <span data-ttu-id="e2c3a-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e2c3a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2c3a-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="e2c3a-113">See also</span></span>

- [<span data-ttu-id="e2c3a-114">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="e2c3a-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
