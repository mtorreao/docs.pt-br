---
title: Método ISymUnmanagedConstant::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: fca7b11a83b5a695feae82fe5f25218f87afbce2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732886"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="9a207-102">Método ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="9a207-102">ISymUnmanagedConstant::GetName Method</span></span>

<span data-ttu-id="9a207-103">Obtém o nome da constante.</span><span class="sxs-lookup"><span data-stu-id="9a207-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a207-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9a207-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a207-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9a207-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="9a207-106">no O comprimento do buffer para o qual o `szName` parâmetro aponta.</span><span class="sxs-lookup"><span data-stu-id="9a207-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9a207-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho, em caracteres, do buffer necessário para conter o nome, incluindo a terminação nula.</span><span class="sxs-lookup"><span data-stu-id="9a207-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="9a207-108">fora O buffer que armazena o nome.</span><span class="sxs-lookup"><span data-stu-id="9a207-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a207-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="9a207-109">Return Value</span></span>  

 <span data-ttu-id="9a207-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="9a207-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a207-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a207-111">Requirements</span></span>  

 <span data-ttu-id="9a207-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9a207-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a207-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="9a207-113">See also</span></span>

- [<span data-ttu-id="9a207-114">Interface ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="9a207-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="9a207-115">Método GetSignature</span><span class="sxs-lookup"><span data-stu-id="9a207-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="9a207-116">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="9a207-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
