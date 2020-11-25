---
title: Método ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707146"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="f41ae-102">Método ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="f41ae-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>

<span data-ttu-id="f41ae-103">Verifica se o método tem informações assíncronas ou não.</span><span class="sxs-lookup"><span data-stu-id="f41ae-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="f41ae-104">Se esse método retornar `FALSE` , ele será inválido para chamar outros métodos nesta interface.</span><span class="sxs-lookup"><span data-stu-id="f41ae-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="f41ae-105">Eles serão retornados `E_UNEXPECTED` nesse caso.</span><span class="sxs-lookup"><span data-stu-id="f41ae-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f41ae-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f41ae-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f41ae-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f41ae-107">Parameters</span></span>  
  
|<span data-ttu-id="f41ae-108">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="f41ae-108">Parameter</span></span>|<span data-ttu-id="f41ae-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="f41ae-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="f41ae-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f41ae-110">Return Value</span></span>  

 <span data-ttu-id="f41ae-111">Retorna `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f41ae-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f41ae-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f41ae-112">Requirements</span></span>  

 <span data-ttu-id="f41ae-113">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f41ae-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f41ae-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="f41ae-114">See also</span></span>

- [<span data-ttu-id="f41ae-115">Interface ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="f41ae-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
