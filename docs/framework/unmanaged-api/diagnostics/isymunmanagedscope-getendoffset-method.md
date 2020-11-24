---
title: Método ISymUnmanagedScope::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 14e747e81e467019d464212e75513bdf98344916
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678357"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="d3d8c-102">Método ISymUnmanagedScope::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="d3d8c-102">ISymUnmanagedScope::GetEndOffset Method</span></span>

<span data-ttu-id="d3d8c-103">Obtém o deslocamento de fim deste escopo.</span><span class="sxs-lookup"><span data-stu-id="d3d8c-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d8c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d3d8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3d8c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d3d8c-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="d3d8c-106">fora Um ponteiro para um `ULONG32` que recebe o deslocamento final.</span><span class="sxs-lookup"><span data-stu-id="d3d8c-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3d8c-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="d3d8c-107">Return Value</span></span>  

 <span data-ttu-id="d3d8c-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="d3d8c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3d8c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3d8c-109">Requirements</span></span>  

 <span data-ttu-id="d3d8c-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d3d8c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d8c-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="d3d8c-111">See also</span></span>

- [<span data-ttu-id="d3d8c-112">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="d3d8c-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="d3d8c-113">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="d3d8c-113">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
