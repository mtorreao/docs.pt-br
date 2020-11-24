---
title: Método ISymUnmanagedDocumentWriter::SetSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
ms.openlocfilehash: 31475b08b569b925aab9cab869545f0912c4ecf8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691585"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="97b81-102">Método ISymUnmanagedDocumentWriter::SetSource</span><span class="sxs-lookup"><span data-stu-id="97b81-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>

<span data-ttu-id="97b81-103">Define a fonte incorporada para um documento que está sendo gravado.</span><span class="sxs-lookup"><span data-stu-id="97b81-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b81-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="97b81-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97b81-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="97b81-105">Parameters</span></span>  

 `sourceSize`  
 <span data-ttu-id="97b81-106">no Um `ULONG32` que contém o tamanho do `source` buffer.</span><span class="sxs-lookup"><span data-stu-id="97b81-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="97b81-107">no O buffer que armazena a fonte inserida.</span><span class="sxs-lookup"><span data-stu-id="97b81-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97b81-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="97b81-108">Return Value</span></span>  

 <span data-ttu-id="97b81-109">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="97b81-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97b81-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97b81-110">Requirements</span></span>  

 <span data-ttu-id="97b81-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="97b81-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b81-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="97b81-112">See also</span></span>

- [<span data-ttu-id="97b81-113">Interface ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="97b81-113">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
