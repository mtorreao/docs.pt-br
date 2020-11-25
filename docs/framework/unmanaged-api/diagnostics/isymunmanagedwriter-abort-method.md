---
title: Método ISymUnmanagedWriter::Abort
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 2136eb32f147b8928e6ac90b99bbdf66804f244d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733263"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="3699b-102">Método ISymUnmanagedWriter::Abort</span><span class="sxs-lookup"><span data-stu-id="3699b-102">ISymUnmanagedWriter::Abort Method</span></span>

<span data-ttu-id="3699b-103">Fecha o gravador de símbolo sem confirmar os símbolos para o repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3699b-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="3699b-104">Após essa chamada, o gravador de símbolo se torna inválido para atualizações adicionais.</span><span class="sxs-lookup"><span data-stu-id="3699b-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="3699b-105">Para confirmar os símbolos e fechar o gravador de símbolo, use o método [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="3699b-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3699b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3699b-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3699b-107">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="3699b-107">Return Value</span></span>  

 <span data-ttu-id="3699b-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="3699b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3699b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3699b-109">Requirements</span></span>  

 <span data-ttu-id="3699b-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3699b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3699b-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="3699b-111">See also</span></span>

- [<span data-ttu-id="3699b-112">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="3699b-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
