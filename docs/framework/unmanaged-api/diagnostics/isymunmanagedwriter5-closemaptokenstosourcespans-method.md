---
title: Método ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
ms.openlocfilehash: b57174f9f76b174927b8f1997beac3dd1482583a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725905"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="8b791-102">Método ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="8b791-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="8b791-103">Feche a seção de dados personalizados especiais para obter informações de mapeamento de token para origem.</span><span class="sxs-lookup"><span data-stu-id="8b791-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="8b791-104">Depois de fechada, não é possível adicionar mais informações de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="8b791-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b791-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8b791-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8b791-106">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="8b791-106">Return Value</span></span>  

 <span data-ttu-id="8b791-107">Retorna `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8b791-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b791-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b791-108">Requirements</span></span>  

 <span data-ttu-id="8b791-109">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8b791-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b791-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="8b791-110">See also</span></span>

- [<span data-ttu-id="8b791-111">Interface ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="8b791-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
