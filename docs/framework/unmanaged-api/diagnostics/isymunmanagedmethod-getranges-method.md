---
title: Método ISymUnmanagedMethod::GetRanges
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
ms.openlocfilehash: 8ed492b573215736c82ab6c231cc5f2e188ea013
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732145"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="9ed5d-102">Método ISymUnmanagedMethod::GetRanges</span><span class="sxs-lookup"><span data-stu-id="9ed5d-102">ISymUnmanagedMethod::GetRanges Method</span></span>

<span data-ttu-id="9ed5d-103">Dada uma posição em um documento, retorna uma matriz de pares de deslocamento inicial e final que correspondem aos intervalos da MSIL (Microsoft Intermediate Language) que a posição aborda nesse método.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="9ed5d-104">A matriz é uma matriz de inteiros e tem o formato [início, fim, início, fim].</span><span class="sxs-lookup"><span data-stu-id="9ed5d-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="9ed5d-105">O número de pares de intervalo é o comprimento da matriz dividida por 2.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed5d-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ed5d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ed5d-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9ed5d-107">Parameters</span></span>  

 `document`  
 <span data-ttu-id="9ed5d-108">no O documento para o qual o deslocamento é solicitado.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="9ed5d-109">no A linha do documento correspondente aos intervalos.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="9ed5d-110">no A coluna de documento correspondente aos intervalos.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="9ed5d-111">no O tamanho da `ranges` matriz.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="9ed5d-112">fora Um ponteiro para um `ULONG32` que recebe o tamanho do buffer necessário para conter os intervalos.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="9ed5d-113">fora Um ponteiro para o buffer que recebe os intervalos.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ed5d-114">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="9ed5d-114">Return Value</span></span>  

 <span data-ttu-id="9ed5d-115">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="9ed5d-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ed5d-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ed5d-116">Requirements</span></span>  

 <span data-ttu-id="9ed5d-117">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9ed5d-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed5d-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="9ed5d-118">See also</span></span>

- [<span data-ttu-id="9ed5d-119">Interface ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="9ed5d-119">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
