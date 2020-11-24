---
title: Método ISymUnmanagedWriter::SetMethodSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: a918b5c2334683348adc6a7382527faedb52d7b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683531"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="cd9d3-102">Método ISymUnmanagedWriter::SetMethodSourceRange</span><span class="sxs-lookup"><span data-stu-id="cd9d3-102">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>

<span data-ttu-id="cd9d3-103">Especifica os verdadeiros início e término de um método de dentro de um arquivo de origem.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-103">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="cd9d3-104">Use esse método para especificar a extensão de um método independentemente dos pontos de sequência que existem dentro do método.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-104">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd9d3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cd9d3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd9d3-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cd9d3-106">Parameters</span></span>  

 `startDoc`  
 <span data-ttu-id="cd9d3-107">no Um ponteiro para o documento que contém a posição inicial.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-107">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="cd9d3-108">no O número da linha inicial.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-108">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="cd9d3-109">no A coluna inicial.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-109">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="cd9d3-110">no Um ponteiro para o documento que contém a posição final.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-110">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="cd9d3-111">no O número da linha final.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-111">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="cd9d3-112">no O número da coluna final.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-112">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd9d3-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="cd9d3-113">Return Value</span></span>  

 <span data-ttu-id="cd9d3-114">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="cd9d3-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd9d3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd9d3-115">Requirements</span></span>  

 <span data-ttu-id="cd9d3-116">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cd9d3-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9d3-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd9d3-117">See also</span></span>

- [<span data-ttu-id="cd9d3-118">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="cd9d3-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
