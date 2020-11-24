---
title: Método ISymUnmanagedWriter::SetUserEntryPoint
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
ms.openlocfilehash: a1c3506758221c3a2b578d93488a4377c1b86a21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683492"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="241a8-102">Método ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="241a8-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>

<span data-ttu-id="241a8-103">Especifica o método definido pelo usuário que é o ponto de entrada para este módulo.</span><span class="sxs-lookup"><span data-stu-id="241a8-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="241a8-104">Por exemplo, esse ponto de entrada pode ser o método Main do usuário em vez de stubs gerados pelo compilador antes de Main.</span><span class="sxs-lookup"><span data-stu-id="241a8-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="241a8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="241a8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="241a8-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="241a8-106">Parameters</span></span>  

 `entryMethod`  
 <span data-ttu-id="241a8-107">no O token de metadados para o método que é o ponto de entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="241a8-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="241a8-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="241a8-108">Return Value</span></span>  

 <span data-ttu-id="241a8-109">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="241a8-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="241a8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="241a8-110">Requirements</span></span>  

 <span data-ttu-id="241a8-111">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="241a8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="241a8-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="241a8-112">See also</span></span>

- [<span data-ttu-id="241a8-113">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="241a8-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
