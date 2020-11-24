---
title: Método ISymUnmanagedReader::GetMethodFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 417644e5d0c7af802d5266bd1825efa83c181597
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689596"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="eea8c-102">Método ISymUnmanagedReader::GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="eea8c-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>

<span data-ttu-id="eea8c-103">Retorna o método que contém o ponto de interrupção na posição especificada em um documento.</span><span class="sxs-lookup"><span data-stu-id="eea8c-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea8c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eea8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eea8c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="eea8c-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="eea8c-106">no O documento especificado.</span><span class="sxs-lookup"><span data-stu-id="eea8c-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="eea8c-107">no A linha do documento especificado.</span><span class="sxs-lookup"><span data-stu-id="eea8c-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="eea8c-108">no A coluna do documento especificado.</span><span class="sxs-lookup"><span data-stu-id="eea8c-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="eea8c-109">fora Um ponteiro para o endereço de um objeto de [interface ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa o método que contém o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="eea8c-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eea8c-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="eea8c-110">Return Value</span></span>  

 <span data-ttu-id="eea8c-111">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="eea8c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eea8c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eea8c-112">Requirements</span></span>  

 <span data-ttu-id="eea8c-113">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="eea8c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eea8c-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="eea8c-114">See also</span></span>

- [<span data-ttu-id="eea8c-115">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="eea8c-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
