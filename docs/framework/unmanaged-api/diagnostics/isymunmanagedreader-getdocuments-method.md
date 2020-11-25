---
title: Método ISymUnmanagedReader::GetDocuments
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
ms.openlocfilehash: 757b7fecbbb187da079c8a5c51462ec58431966f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707614"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="3947c-102">Método ISymUnmanagedReader::GetDocuments</span><span class="sxs-lookup"><span data-stu-id="3947c-102">ISymUnmanagedReader::GetDocuments Method</span></span>

<span data-ttu-id="3947c-103">Retorna uma matriz de todos os documentos definidos no repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3947c-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3947c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3947c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3947c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3947c-105">Parameters</span></span>  

 `cDocs`  
 <span data-ttu-id="3947c-106">no O tamanho da `pDocs` matriz.</span><span class="sxs-lookup"><span data-stu-id="3947c-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="3947c-107">fora Um ponteiro para uma variável que recebe o comprimento da matriz.</span><span class="sxs-lookup"><span data-stu-id="3947c-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="3947c-108">fora Um ponteiro para uma variável que recebe a matriz de documentos.</span><span class="sxs-lookup"><span data-stu-id="3947c-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3947c-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="3947c-109">Return Value</span></span>  

 <span data-ttu-id="3947c-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="3947c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3947c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3947c-111">Requirements</span></span>  

 <span data-ttu-id="3947c-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3947c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3947c-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="3947c-113">See also</span></span>

- [<span data-ttu-id="3947c-114">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="3947c-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
