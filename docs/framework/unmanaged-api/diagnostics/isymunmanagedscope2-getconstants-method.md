---
title: Método ISymUnmanagedScope2::GetConstants
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: df42e58a9bb3bf00b3fa4df45086dc2219658e25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725840"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="835f7-102">Método ISymUnmanagedScope2::GetConstants</span><span class="sxs-lookup"><span data-stu-id="835f7-102">ISymUnmanagedScope2::GetConstants Method</span></span>

<span data-ttu-id="835f7-103">Obtém as constantes locais definidas neste escopo.</span><span class="sxs-lookup"><span data-stu-id="835f7-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="835f7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="835f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="835f7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="835f7-105">Parameters</span></span>  

 `cConstants`  
 <span data-ttu-id="835f7-106">no O comprimento do buffer para o qual o `pcConstants` parâmetro aponta.</span><span class="sxs-lookup"><span data-stu-id="835f7-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="835f7-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho, em caracteres, do buffer necessário para conter as constantes.</span><span class="sxs-lookup"><span data-stu-id="835f7-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="835f7-108">fora O buffer que armazena as constantes.</span><span class="sxs-lookup"><span data-stu-id="835f7-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="835f7-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="835f7-109">Return Value</span></span>  

 <span data-ttu-id="835f7-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="835f7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="835f7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="835f7-111">Requirements</span></span>  

 <span data-ttu-id="835f7-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="835f7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="835f7-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="835f7-113">See also</span></span>

- [<span data-ttu-id="835f7-114">Interface ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="835f7-114">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
