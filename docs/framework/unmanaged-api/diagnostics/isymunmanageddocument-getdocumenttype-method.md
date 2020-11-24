---
title: Método ISymUnmanagedDocument::GetDocumentType
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
ms.openlocfilehash: d30ee9318d76aaf3ad2cde789ae292aed54f457e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689674"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="f6599-102">Método ISymUnmanagedDocument::GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="f6599-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>

<span data-ttu-id="f6599-103">Obtém o tipo de documento deste documento.</span><span class="sxs-lookup"><span data-stu-id="f6599-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6599-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f6599-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6599-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f6599-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="f6599-106">fora Ponteiro para uma variável que recebe o tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="f6599-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6599-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f6599-107">Return Value</span></span>  

 <span data-ttu-id="f6599-108">S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="f6599-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6599-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="f6599-109">See also</span></span>

- [<span data-ttu-id="f6599-110">Interface ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="f6599-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
