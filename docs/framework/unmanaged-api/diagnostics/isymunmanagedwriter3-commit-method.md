---
title: Método ISymUnmanagedWriter3::Commit
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
ms.openlocfilehash: 394832d6144509717d2f79a78afaff50ad81c01d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683297"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="f6ad6-102">Método ISymUnmanagedWriter3::Commit</span><span class="sxs-lookup"><span data-stu-id="f6ad6-102">ISymUnmanagedWriter3::Commit Method</span></span>

<span data-ttu-id="f6ad6-103">Confirma as alterações gravadas até o fluxo.</span><span class="sxs-lookup"><span data-stu-id="f6ad6-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ad6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f6ad6-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f6ad6-105">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="f6ad6-105">Return Value</span></span>  

 <span data-ttu-id="f6ad6-106">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="f6ad6-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6ad6-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6ad6-107">Requirements</span></span>  

 <span data-ttu-id="f6ad6-108">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f6ad6-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ad6-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="f6ad6-109">See also</span></span>

- [<span data-ttu-id="f6ad6-110">Interface ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="f6ad6-110">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
