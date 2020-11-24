---
title: Método ISymUnmanagedReader::GetMethodsFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: 5298dd0f53693d96b748f6c839660838fdfad4ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689544"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="c6c3a-102">Método ISymUnmanagedReader::GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="c6c3a-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>

<span data-ttu-id="c6c3a-103">Retorna uma matriz de métodos, cada um contendo o ponto de interrupção na posição especificada em um documento.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c3a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c6c3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6c3a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c6c3a-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="c6c3a-106">no O documento especificado.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="c6c3a-107">no A linha do documento especificado.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="c6c3a-108">no A coluna do documento especificado.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="c6c3a-109">no O tamanho da `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="c6c3a-110">fora Um ponteiro para uma variável que recebe o número de elementos retornados na `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c6c3a-111">fora Uma matriz de ponteiros, cada um dos quais aponta para um objeto [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa um método que contém o ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6c3a-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="c6c3a-112">Return Value</span></span>  

 <span data-ttu-id="c6c3a-113">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="c6c3a-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c3a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6c3a-114">Requirements</span></span>  

 <span data-ttu-id="c6c3a-115">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c6c3a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c3a-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="c6c3a-116">See also</span></span>

- [<span data-ttu-id="c6c3a-117">Interface ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="c6c3a-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
