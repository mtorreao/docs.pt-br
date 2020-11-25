---
title: Método ISymUnmanagedVariable::GetAddressKind
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
ms.openlocfilehash: 6a7824949edc905a3edcd58f60d40f8b1a40c53c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726906"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="70550-102">Método ISymUnmanagedVariable::GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="70550-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>

<span data-ttu-id="70550-103">Obtém o tipo de endereço dessa variável.</span><span class="sxs-lookup"><span data-stu-id="70550-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70550-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="70550-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70550-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="70550-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="70550-106">fora Um ponteiro para um `ULONG32` que recebe o valor.</span><span class="sxs-lookup"><span data-stu-id="70550-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="70550-107">Os valores possíveis são definidos na enumeração [CorSymAddrKind](corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="70550-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70550-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="70550-108">Return Value</span></span>  

 <span data-ttu-id="70550-109">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="70550-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70550-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70550-110">Requirements</span></span>  

 <span data-ttu-id="70550-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="70550-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70550-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="70550-112">See also</span></span>

- [<span data-ttu-id="70550-113">Interface ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="70550-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
