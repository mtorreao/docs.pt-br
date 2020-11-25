---
title: Método ISymUnmanagedWriter5::MapTokenToSourceSpan
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: e4b09e6d89b3ba8ba3bf7e149d31a14a74b945b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723929"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="91140-102">Método ISymUnmanagedWriter5::MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="91140-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>

<span data-ttu-id="91140-103">Mapeia o token de metadados fornecido para o span de linha de origem fornecido no arquivo de origem especificado.</span><span class="sxs-lookup"><span data-stu-id="91140-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="91140-104">Deve ser chamado entre as chamadas para o [método OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e o [método CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="91140-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91140-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="91140-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91140-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="91140-106">Parameters</span></span>  
  
|<span data-ttu-id="91140-107">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="91140-107">Parameter</span></span>|<span data-ttu-id="91140-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="91140-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="91140-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="91140-109">Return Value</span></span>  

 <span data-ttu-id="91140-110">Retorna `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="91140-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91140-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91140-111">Requirements</span></span>  

 <span data-ttu-id="91140-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="91140-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91140-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="91140-113">See also</span></span>

- [<span data-ttu-id="91140-114">Interface ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="91140-114">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
