---
title: Método ISymUnmanagedVariable::GetAddressField1
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: e3ea3c0fd65750d52c0cfb10edbe18b1512f724b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729012"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="5b574-102">Método ISymUnmanagedVariable::GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="5b574-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>

<span data-ttu-id="5b574-103">Obtém o primeiro campo de endereço para essa variável.</span><span class="sxs-lookup"><span data-stu-id="5b574-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="5b574-104">Seu significado depende do tipo de endereço.</span><span class="sxs-lookup"><span data-stu-id="5b574-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b574-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5b574-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b574-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5b574-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="5b574-107">fora Um ponteiro para um `ULONG32` que recebe o primeiro campo de endereço.</span><span class="sxs-lookup"><span data-stu-id="5b574-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b574-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="5b574-108">Return Value</span></span>  

 <span data-ttu-id="5b574-109">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="5b574-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b574-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b574-110">Requirements</span></span>  

 <span data-ttu-id="5b574-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5b574-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b574-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="5b574-112">See also</span></span>

- [<span data-ttu-id="5b574-113">Interface ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="5b574-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="5b574-114">Método GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="5b574-114">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="5b574-115">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="5b574-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="5b574-116">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="5b574-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
