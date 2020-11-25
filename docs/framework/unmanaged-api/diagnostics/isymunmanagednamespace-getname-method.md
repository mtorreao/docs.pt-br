---
title: Método ISymUnmanagedNamespace::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: eca1137fb607d64e8645de5b0afc7ca391eac763
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699255"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="0e22d-102">Método ISymUnmanagedNamespace::GetName</span><span class="sxs-lookup"><span data-stu-id="0e22d-102">ISymUnmanagedNamespace::GetName Method</span></span>

<span data-ttu-id="0e22d-103">Obtém o nome deste namespace.</span><span class="sxs-lookup"><span data-stu-id="0e22d-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e22d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0e22d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e22d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0e22d-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="0e22d-106">no Um `ULONG32` que indica o tamanho do `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="0e22d-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0e22d-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho, em caracteres, do buffer necessário para conter o nome do namespace, incluindo a terminação nula.</span><span class="sxs-lookup"><span data-stu-id="0e22d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="0e22d-108">fora Um ponteiro para um buffer que contém o nome do namespace.</span><span class="sxs-lookup"><span data-stu-id="0e22d-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e22d-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="0e22d-109">Return Value</span></span>  

 <span data-ttu-id="0e22d-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="0e22d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e22d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e22d-111">Requirements</span></span>  

 <span data-ttu-id="0e22d-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0e22d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e22d-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="0e22d-113">See also</span></span>

- [<span data-ttu-id="0e22d-114">Interface ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="0e22d-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
