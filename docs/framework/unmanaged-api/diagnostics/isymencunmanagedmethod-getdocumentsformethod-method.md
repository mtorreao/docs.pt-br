---
title: Método ISymENCUnmanagedMethod::GetDocumentsForMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: d9fe18225dc27e93d4e97940cba878e4d73b4ed2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730520"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="891dd-102">Método ISymENCUnmanagedMethod::GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="891dd-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>

<span data-ttu-id="891dd-103">Obtém os documentos em que este método tem linhas.</span><span class="sxs-lookup"><span data-stu-id="891dd-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="891dd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="891dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="891dd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="891dd-105">Parameters</span></span>  

 `cDocs`  
 <span data-ttu-id="891dd-106">no O comprimento do buffer apontado por `pcDocs` .</span><span class="sxs-lookup"><span data-stu-id="891dd-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="891dd-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho, em caracteres, do buffer necessário para conter os documentos.</span><span class="sxs-lookup"><span data-stu-id="891dd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="891dd-108">no O buffer que contém os documentos.</span><span class="sxs-lookup"><span data-stu-id="891dd-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="891dd-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="891dd-109">Return Value</span></span>  

 <span data-ttu-id="891dd-110">S_OK se o método tiver sucesso; caso contrário, um código de erro.</span><span class="sxs-lookup"><span data-stu-id="891dd-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="891dd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="891dd-111">Requirements</span></span>  

 <span data-ttu-id="891dd-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="891dd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891dd-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="891dd-113">See also</span></span>

- [<span data-ttu-id="891dd-114">Interface ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="891dd-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
