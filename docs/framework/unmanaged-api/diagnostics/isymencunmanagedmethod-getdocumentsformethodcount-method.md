---
title: Método ISymENCUnmanagedMethod::GetDocumentsForMethodCount
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
ms.openlocfilehash: 53897b6f964afb1f8ca95bc8f93c532e148ad129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730507"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="651e2-102">Método ISymENCUnmanagedMethod::GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="651e2-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>

<span data-ttu-id="651e2-103">Obtém o número de documentos em que esse método tem linhas.</span><span class="sxs-lookup"><span data-stu-id="651e2-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="651e2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="651e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="651e2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="651e2-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="651e2-106">fora Um ponteiro para um `ULONG32` que recebe o tamanho do buffer necessário para conter os documentos.</span><span class="sxs-lookup"><span data-stu-id="651e2-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="651e2-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="651e2-107">Return Value</span></span>  

 <span data-ttu-id="651e2-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="651e2-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="651e2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="651e2-109">Requirements</span></span>  

 <span data-ttu-id="651e2-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="651e2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651e2-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="651e2-111">See also</span></span>

- [<span data-ttu-id="651e2-112">Interface ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="651e2-112">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
