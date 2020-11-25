---
title: Método ISymUnmanagedDocument::GetURL
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
ms.openlocfilehash: c862b6d3bfa415b622b68898db1ff30c6759e8f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726932"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="4d996-102">Método ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="4d996-102">ISymUnmanagedDocument::GetURL Method</span></span>

<span data-ttu-id="4d996-103">Retorna o Uniform Resource Locator (URL) deste documento.</span><span class="sxs-lookup"><span data-stu-id="4d996-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d996-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4d996-104">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d996-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4d996-105">Parameters</span></span>  

 `cchUrl`  
 <span data-ttu-id="4d996-106">no O tamanho, em caracteres, do `szURL` buffer.</span><span class="sxs-lookup"><span data-stu-id="4d996-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="4d996-107">fora Um ponteiro para uma variável que recebe o tamanho da URL, incluindo a terminação nula.</span><span class="sxs-lookup"><span data-stu-id="4d996-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="4d996-108">fora O buffer que contém a URL.</span><span class="sxs-lookup"><span data-stu-id="4d996-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d996-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="4d996-109">Return Value</span></span>  

 <span data-ttu-id="4d996-110">S_OK se o método tiver sucesso; caso contrário, um código de erro.</span><span class="sxs-lookup"><span data-stu-id="4d996-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d996-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d996-111">See also</span></span>

- [<span data-ttu-id="4d996-112">Interface ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="4d996-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
