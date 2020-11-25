---
title: Método ISymUnmanagedConstant::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: 4436e4528c1dc486eb5c443c5a9467ac69a26c7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706925"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="25615-102">Método ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="25615-102">ISymUnmanagedConstant::GetSignature Method</span></span>

<span data-ttu-id="25615-103">Obtém a assinatura da constante.</span><span class="sxs-lookup"><span data-stu-id="25615-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25615-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="25615-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25615-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="25615-105">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="25615-106">no O comprimento do buffer para o qual o `pcSig` parâmetro aponta.</span><span class="sxs-lookup"><span data-stu-id="25615-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="25615-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho, em caracteres, do buffer necessário para conter a assinatura.</span><span class="sxs-lookup"><span data-stu-id="25615-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="25615-108">fora O buffer que armazena a assinatura.</span><span class="sxs-lookup"><span data-stu-id="25615-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25615-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="25615-109">Return Value</span></span>  

 <span data-ttu-id="25615-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="25615-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25615-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25615-111">Requirements</span></span>  

 <span data-ttu-id="25615-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="25615-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25615-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="25615-113">See also</span></span>

- [<span data-ttu-id="25615-114">Interface ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="25615-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="25615-115">Método GetName</span><span class="sxs-lookup"><span data-stu-id="25615-115">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="25615-116">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="25615-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
