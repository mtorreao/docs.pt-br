---
title: Método ISymUnmanagedScope::GetMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
ms.openlocfilehash: 75d5638a6f01ba9569a03e5255a7217371c9d177
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725931"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="ac430-102">Método ISymUnmanagedScope::GetMethod</span><span class="sxs-lookup"><span data-stu-id="ac430-102">ISymUnmanagedScope::GetMethod Method</span></span>

<span data-ttu-id="ac430-103">Obtém o método que contém esse escopo.</span><span class="sxs-lookup"><span data-stu-id="ac430-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac430-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ac430-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac430-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ac430-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="ac430-106">fora Um ponteiro para a interface [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) retornada.</span><span class="sxs-lookup"><span data-stu-id="ac430-106">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac430-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="ac430-107">Return Value</span></span>  

 <span data-ttu-id="ac430-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="ac430-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac430-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac430-109">Requirements</span></span>  

 <span data-ttu-id="ac430-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ac430-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac430-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="ac430-111">See also</span></span>

- [<span data-ttu-id="ac430-112">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="ac430-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
