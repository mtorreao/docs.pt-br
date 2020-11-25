---
title: Método ISymUnmanagedReader::GetDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
ms.openlocfilehash: 4604d78f66b872a30457c51bf65890caf613c4fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707627"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="fc5fa-102">Método ISymUnmanagedReader::GetDocument</span><span class="sxs-lookup"><span data-stu-id="fc5fa-102">ISymUnmanagedReader::GetDocument Method</span></span>

<span data-ttu-id="fc5fa-103">Localiza um documento.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-103">Finds a document.</span></span> <span data-ttu-id="fc5fa-104">O idioma do documento, o fornecedor e o tipo são opcionais.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc5fa-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fc5fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc5fa-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fc5fa-106">Parameters</span></span>  

 `url`  
 <span data-ttu-id="fc5fa-107">no A URL que identifica o documento.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="fc5fa-108">no O idioma do documento.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-108">[in] The document language.</span></span> <span data-ttu-id="fc5fa-109">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="fc5fa-110">no A identidade do fornecedor para o idioma do documento.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="fc5fa-111">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="fc5fa-112">no O tipo do documento.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-112">[in] The type of the document.</span></span> <span data-ttu-id="fc5fa-113">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fc5fa-114">fora Um ponteiro para a interface retornada.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc5fa-115">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="fc5fa-115">Return Value</span></span>  

 <span data-ttu-id="fc5fa-116">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc5fa-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc5fa-117">Requirements</span></span>  

 <span data-ttu-id="fc5fa-118">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="fc5fa-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5fa-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="fc5fa-119">See also</span></span>

- [<span data-ttu-id="fc5fa-120">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="fc5fa-120">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
