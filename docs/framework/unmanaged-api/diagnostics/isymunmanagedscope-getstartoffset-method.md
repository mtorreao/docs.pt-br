---
title: Método ISymUnmanagedScope::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
ms.openlocfilehash: 69b72ce66a203f403fcfe0fd4b4e728ece7397e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725866"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="3d521-102">Método ISymUnmanagedScope::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="3d521-102">ISymUnmanagedScope::GetStartOffset Method</span></span>

<span data-ttu-id="3d521-103">Obtém o deslocamento inicial para este escopo.</span><span class="sxs-lookup"><span data-stu-id="3d521-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d521-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3d521-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d521-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3d521-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="3d521-106">fora Um ponteiro para um `ULONG32` que contém o deslocamento inicial.</span><span class="sxs-lookup"><span data-stu-id="3d521-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d521-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="3d521-107">Return Value</span></span>  

 <span data-ttu-id="3d521-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="3d521-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d521-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d521-109">Requirements</span></span>  

 <span data-ttu-id="3d521-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3d521-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d521-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="3d521-111">See also</span></span>

- [<span data-ttu-id="3d521-112">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="3d521-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="3d521-113">Método GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="3d521-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
