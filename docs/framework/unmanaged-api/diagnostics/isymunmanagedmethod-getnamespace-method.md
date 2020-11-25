---
title: Método ISymUnmanagedMethod::GetNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: 7e26c272ee1ecf03f7d2a347cf7ca2cc3efa2122
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699554"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="516d4-102">Método ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="516d4-102">ISymUnmanagedMethod::GetNamespace Method</span></span>

<span data-ttu-id="516d4-103">Obtém o namespace no qual esse método é definido.</span><span class="sxs-lookup"><span data-stu-id="516d4-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="516d4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="516d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="516d4-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="516d4-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="516d4-106">fora Um ponteiro que é definido para a interface [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) retornada.</span><span class="sxs-lookup"><span data-stu-id="516d4-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="516d4-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="516d4-107">Return Value</span></span>  

 <span data-ttu-id="516d4-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="516d4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="516d4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="516d4-109">Requirements</span></span>  

 <span data-ttu-id="516d4-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="516d4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="516d4-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="516d4-111">See also</span></span>

- [<span data-ttu-id="516d4-112">Interface ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="516d4-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
