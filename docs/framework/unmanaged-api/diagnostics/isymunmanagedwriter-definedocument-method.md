---
title: Método ISymUnmanagedWriter::DefineDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
ms.openlocfilehash: 6413935df86b85a959fa4f354c6233d18baf99d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727569"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a><span data-ttu-id="7d8be-102">Método ISymUnmanagedWriter::DefineDocument</span><span class="sxs-lookup"><span data-stu-id="7d8be-102">ISymUnmanagedWriter::DefineDocument Method</span></span>

<span data-ttu-id="7d8be-103">Define um documento de origem.</span><span class="sxs-lookup"><span data-stu-id="7d8be-103">Defines a source document.</span></span> <span data-ttu-id="7d8be-104">Os GUIDs são fornecidos para idiomas, fornecedores e tipos de documentos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="7d8be-104">GUIDs are provided for known languages, vendors, and document types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d8be-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7d8be-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d8be-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7d8be-106">Parameters</span></span>  

 `url`  
 <span data-ttu-id="7d8be-107">no Um ponteiro para um `WCHAR` que define o Uniform Resource Locator (URL) que identifica o documento.</span><span class="sxs-lookup"><span data-stu-id="7d8be-107">[in] A pointer to a `WCHAR` that defines the uniform resource locator (URL) that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="7d8be-108">no Um ponteiro para um GUID que define o idioma do documento.</span><span class="sxs-lookup"><span data-stu-id="7d8be-108">[in] A pointer to a GUID that defines the document language.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="7d8be-109">no Um ponteiro para um GUID que define a identidade do fornecedor para o idioma do documento.</span><span class="sxs-lookup"><span data-stu-id="7d8be-109">[in] A pointer to a GUID that defines the identity of the vendor for the document language.</span></span>  
  
 `documentType`  
 <span data-ttu-id="7d8be-110">no Um ponteiro para um GUID que define o tipo do documento.</span><span class="sxs-lookup"><span data-stu-id="7d8be-110">[in] A pointer to a GUID that defines the type of the document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7d8be-111">fora Um ponteiro para a interface [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) retornada.</span><span class="sxs-lookup"><span data-stu-id="7d8be-111">[out] A pointer to the returned [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d8be-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="7d8be-112">Return Value</span></span>  

 <span data-ttu-id="7d8be-113">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="7d8be-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d8be-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d8be-114">Requirements</span></span>  

 <span data-ttu-id="7d8be-115">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7d8be-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8be-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="7d8be-116">See also</span></span>

- [<span data-ttu-id="7d8be-117">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="7d8be-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
