---
title: Método ISymUnmanagedWriter::Close
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 1d684c14f14fcc93040798ae4ee3b8bb1df5354d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733250"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="8be03-102">Método ISymUnmanagedWriter::Close</span><span class="sxs-lookup"><span data-stu-id="8be03-102">ISymUnmanagedWriter::Close Method</span></span>

<span data-ttu-id="8be03-103">Fecha o gravador de símbolo depois de confirmar os símbolos para o repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="8be03-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be03-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8be03-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8be03-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="8be03-105">Return Value</span></span>  

 <span data-ttu-id="8be03-106">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="8be03-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8be03-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="8be03-107">Remarks</span></span>  

 <span data-ttu-id="8be03-108">Após essa chamada, o gravador de símbolo se torna inválido para atualizações adicionais.</span><span class="sxs-lookup"><span data-stu-id="8be03-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="8be03-109">Para fechar o gravador de símbolo sem confirmar os símbolos, use o método [ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="8be03-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be03-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8be03-110">Requirements</span></span>  

 <span data-ttu-id="8be03-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8be03-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be03-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="8be03-112">See also</span></span>

- [<span data-ttu-id="8be03-113">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8be03-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
