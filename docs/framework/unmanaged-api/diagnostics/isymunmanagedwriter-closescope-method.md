---
title: Método ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 561a6348b9976789b02961fadb37d9127f5a6a13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713035"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="ee12d-102">Método ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="ee12d-102">ISymUnmanagedWriter::CloseScope Method</span></span>

<span data-ttu-id="ee12d-103">Fecha o escopo léxico atual.</span><span class="sxs-lookup"><span data-stu-id="ee12d-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee12d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ee12d-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee12d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ee12d-105">Parameters</span></span>  

 `endOffset`  
 <span data-ttu-id="ee12d-106">no O deslocamento do início do método do ponto no final da última instrução no escopo léxico, em bytes.</span><span class="sxs-lookup"><span data-stu-id="ee12d-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee12d-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="ee12d-107">Return Value</span></span>  

 <span data-ttu-id="ee12d-108">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="ee12d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee12d-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="ee12d-109">Remarks</span></span>  

 <span data-ttu-id="ee12d-110">Depois que um escopo é fechado, nenhuma outra variável pode ser definida dentro dele.</span><span class="sxs-lookup"><span data-stu-id="ee12d-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="ee12d-111">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) retorna um identificador de escopo opaco que pode ser usado com [ISymUnmanagedWriter:: SetScopeRange](isymunmanagedwriter-setscoperange-method.md) para definir posteriormente o deslocamento de início e de término do escopo.</span><span class="sxs-lookup"><span data-stu-id="ee12d-111">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="ee12d-112">Nesse caso, os deslocamentos passados para `ISymUnmanagedWriter::OpenScope` e `ISymUnmanagedWriter::CloseScope` são ignorados.</span><span class="sxs-lookup"><span data-stu-id="ee12d-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="ee12d-113">Os identificadores de escopo são válidos somente no método atual.</span><span class="sxs-lookup"><span data-stu-id="ee12d-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee12d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee12d-114">Requirements</span></span>  

 <span data-ttu-id="ee12d-115">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ee12d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee12d-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee12d-116">See also</span></span>

- [<span data-ttu-id="ee12d-117">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ee12d-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
