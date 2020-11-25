---
title: Método ISymUnmanagedReader::GetSymbolStoreFileName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
ms.openlocfilehash: df503e44f20a0b1f02e2c609cc4b52712520faea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720562"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="3b450-102">Método ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="3b450-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>

<span data-ttu-id="3b450-103">Fornece o nome de arquivo em disco do repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3b450-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b450-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3b450-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b450-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3b450-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="3b450-106">no O tamanho do `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="3b450-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3b450-107">fora Um ponteiro para a variável que recebe o comprimento do nome retornado no `szName` , incluindo a terminação nula.</span><span class="sxs-lookup"><span data-stu-id="3b450-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="3b450-108">fora Um ponteiro para a variável que recebe o nome de arquivo do repositório de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3b450-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b450-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="3b450-109">Return Value</span></span>  

 <span data-ttu-id="3b450-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="3b450-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b450-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b450-111">Requirements</span></span>  

 <span data-ttu-id="3b450-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3b450-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b450-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b450-113">See also</span></span>

- [<span data-ttu-id="3b450-114">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="3b450-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
