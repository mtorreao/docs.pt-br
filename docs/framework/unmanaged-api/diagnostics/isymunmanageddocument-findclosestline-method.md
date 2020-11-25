---
title: Método ISymUnmanagedDocument::FindClosestLine
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 5ec67758e3174493cbd5cec1de0dcce30013ac43
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698579"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="643f0-102">Método ISymUnmanagedDocument::FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="643f0-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>

<span data-ttu-id="643f0-103">Retorna a linha mais próxima que é um ponto de sequência, dada uma linha neste documento que pode ou não ser um ponto de sequência.</span><span class="sxs-lookup"><span data-stu-id="643f0-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="643f0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="643f0-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="643f0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="643f0-105">Parameters</span></span>  

 `line`  
 <span data-ttu-id="643f0-106">no Uma linha neste documento.</span><span class="sxs-lookup"><span data-stu-id="643f0-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="643f0-107">fora Um ponteiro para uma variável que recebe a linha.</span><span class="sxs-lookup"><span data-stu-id="643f0-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="643f0-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="643f0-108">Return Value</span></span>  

 <span data-ttu-id="643f0-109">S_OK se o método tiver sucesso; caso contrário, um código de erro.</span><span class="sxs-lookup"><span data-stu-id="643f0-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643f0-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="643f0-110">See also</span></span>

- [<span data-ttu-id="643f0-111">Interface ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="643f0-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
