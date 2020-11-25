---
title: Método ISymUnmanagedENCUpdate::GetLocalVariableCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: 19e07fb181f631335a0c56bd59b6fc8e14e2f36d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726919"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="09fd0-102">Método ISymUnmanagedENCUpdate::GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="09fd0-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>

<span data-ttu-id="09fd0-103">Obtém o número de variáveis locais.</span><span class="sxs-lookup"><span data-stu-id="09fd0-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09fd0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="09fd0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09fd0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="09fd0-105">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="09fd0-106">no O token de metadados dos métodos.</span><span class="sxs-lookup"><span data-stu-id="09fd0-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="09fd0-107">fora Um ponteiro para um `ULONG32` que recebe o tamanho, em caracteres, do buffer necessário para conter o número de variáveis locais.</span><span class="sxs-lookup"><span data-stu-id="09fd0-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09fd0-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="09fd0-108">Return Value</span></span>  

 <span data-ttu-id="09fd0-109">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="09fd0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09fd0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09fd0-110">Requirements</span></span>  

 <span data-ttu-id="09fd0-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="09fd0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fd0-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="09fd0-112">See also</span></span>

- [<span data-ttu-id="09fd0-113">Interface ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="09fd0-113">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
