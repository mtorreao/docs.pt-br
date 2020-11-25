---
title: Método ISymUnmanagedScope::GetLocalCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 07c41e9d80b1703e86ae06525d64bf166ef2cf8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717546"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="6b13c-102">Método ISymUnmanagedScope::GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="6b13c-102">ISymUnmanagedScope::GetLocalCount Method</span></span>

<span data-ttu-id="6b13c-103">Obtém uma contagem das variáveis locais definidas neste escopo.</span><span class="sxs-lookup"><span data-stu-id="6b13c-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b13c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6b13c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b13c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6b13c-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="6b13c-106">fora Um ponteiro para um `ULONG32` que recebe a contagem de variáveis locais.</span><span class="sxs-lookup"><span data-stu-id="6b13c-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b13c-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="6b13c-107">Return Value</span></span>  

 <span data-ttu-id="6b13c-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="6b13c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b13c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b13c-109">Requirements</span></span>  

 <span data-ttu-id="6b13c-110">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6b13c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b13c-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="6b13c-111">See also</span></span>

- [<span data-ttu-id="6b13c-112">Interface ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="6b13c-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
