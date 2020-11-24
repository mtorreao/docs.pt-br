---
title: Método ISymUnmanagedReader::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
ms.openlocfilehash: c4341a5ffe557694473ae505590b57d39a27a721
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675887"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="42cc8-102">Método ISymUnmanagedReader::GetVariables</span><span class="sxs-lookup"><span data-stu-id="42cc8-102">ISymUnmanagedReader::GetVariables Method</span></span>

<span data-ttu-id="42cc8-103">Retorna uma variável não local, dado seu pai e nome.</span><span class="sxs-lookup"><span data-stu-id="42cc8-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42cc8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="42cc8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42cc8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="42cc8-105">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="42cc8-106">no O pai da variável.</span><span class="sxs-lookup"><span data-stu-id="42cc8-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="42cc8-107">no O tamanho da `pVars` matriz.</span><span class="sxs-lookup"><span data-stu-id="42cc8-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="42cc8-108">fora Um ponteiro para a variável que recebe o número de variáveis retornadas em `pVars` .</span><span class="sxs-lookup"><span data-stu-id="42cc8-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="42cc8-109">fora Um ponteiro para a variável que recebe as variáveis.</span><span class="sxs-lookup"><span data-stu-id="42cc8-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42cc8-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="42cc8-110">Return Value</span></span>  

 <span data-ttu-id="42cc8-111">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="42cc8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42cc8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42cc8-112">Requirements</span></span>  

 <span data-ttu-id="42cc8-113">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="42cc8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42cc8-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="42cc8-114">See also</span></span>

- [<span data-ttu-id="42cc8-115">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="42cc8-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
