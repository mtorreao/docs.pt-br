---
title: Método ISymUnmanagedDispose::Destroy
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
ms.openlocfilehash: 6a31026f5b1669c0c29762048dc2c5c1c7bbb6a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732821"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="40c3f-102">Método ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="40c3f-102">ISymUnmanagedDispose::Destroy Method</span></span>

<span data-ttu-id="40c3f-103">Faz com que o objeto subjacente libere todas as referências internas e retorne a falha em qualquer chamada de método subsequente.</span><span class="sxs-lookup"><span data-stu-id="40c3f-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c3f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="40c3f-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="40c3f-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="40c3f-105">Return Value</span></span>  

 <span data-ttu-id="40c3f-106">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="40c3f-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40c3f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40c3f-107">Requirements</span></span>  

 <span data-ttu-id="40c3f-108">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="40c3f-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c3f-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="40c3f-109">See also</span></span>

- [<span data-ttu-id="40c3f-110">Interface ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="40c3f-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
