---
title: Método ISymUnmanagedSymbolSearchInfo::GetSearchPath
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
ms.openlocfilehash: eda8a7ff1d8b3031173bf5f73a8b8a8355e6a62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705521"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="df02d-102">Método ISymUnmanagedSymbolSearchInfo::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="df02d-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>

<span data-ttu-id="df02d-103">Obtém o caminho de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df02d-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df02d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df02d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df02d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="df02d-105">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="df02d-106">fora Um ponteiro para um `ULONG32` que recebe o tamanho, em caracteres, do buffer necessário para conter o caminho de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df02d-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df02d-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="df02d-107">Return Value</span></span>  

 <span data-ttu-id="df02d-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="df02d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df02d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df02d-109">Requirements</span></span>  

 <span data-ttu-id="df02d-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="df02d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df02d-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="df02d-111">See also</span></span>

- [<span data-ttu-id="df02d-112">Interface ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="df02d-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
