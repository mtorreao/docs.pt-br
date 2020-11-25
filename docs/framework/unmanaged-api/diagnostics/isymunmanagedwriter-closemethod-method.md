---
title: Método ISymUnmanagedWriter::CloseMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
ms.openlocfilehash: fcf250f10baf4c65cd1c8c918655e4b9f4f5cc4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731729"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="87db2-102">Método ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="87db2-102">ISymUnmanagedWriter::CloseMethod Method</span></span>

<span data-ttu-id="87db2-103">Fecha o método atual.</span><span class="sxs-lookup"><span data-stu-id="87db2-103">Closes the current method.</span></span> <span data-ttu-id="87db2-104">Depois que um método é fechado, nenhum símbolo pode ser definido dentro dele.</span><span class="sxs-lookup"><span data-stu-id="87db2-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87db2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="87db2-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="87db2-106">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="87db2-106">Return Value</span></span>  

 <span data-ttu-id="87db2-107">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="87db2-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87db2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87db2-108">Requirements</span></span>  

 <span data-ttu-id="87db2-109">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="87db2-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87db2-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="87db2-110">See also</span></span>

- [<span data-ttu-id="87db2-111">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="87db2-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="87db2-112">Método OpenMethod</span><span class="sxs-lookup"><span data-stu-id="87db2-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
