---
title: Método ISymUnmanagedMethod::GetSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
ms.openlocfilehash: 38763e687c66dcb038a874c9c17cb0d67e547816
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699346"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="7a469-102">Método ISymUnmanagedMethod::GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="7a469-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>

<span data-ttu-id="7a469-103">Obtém todos os pontos de sequência dentro deste método.</span><span class="sxs-lookup"><span data-stu-id="7a469-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a469-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7a469-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a469-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7a469-105">Parameters</span></span>  

 `cPoints`  
 <span data-ttu-id="7a469-106">no Um `ULONG32` que recebe o tamanho das `offsets` `documents` matrizes,, `lines` ,, `columns` `endLines` e `endColumns` .</span><span class="sxs-lookup"><span data-stu-id="7a469-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="7a469-107">fora Um ponteiro para um `ULONG32` que recebe o comprimento do buffer necessário para conter os pontos de sequência.</span><span class="sxs-lookup"><span data-stu-id="7a469-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="7a469-108">no Uma matriz na qual armazenar os deslocamentos da MSIL (Microsoft Intermediate Language) do início do método para os pontos de sequência.</span><span class="sxs-lookup"><span data-stu-id="7a469-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="7a469-109">no Uma matriz na qual armazenar os documentos nos quais os pontos de sequência estão localizados.</span><span class="sxs-lookup"><span data-stu-id="7a469-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="7a469-110">no Uma matriz na qual armazenar as linhas nos documentos nos quais os pontos de sequência estão localizados.</span><span class="sxs-lookup"><span data-stu-id="7a469-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="7a469-111">no Uma matriz na qual armazenar as colunas nos documentos nos quais os pontos de sequência estão localizados.</span><span class="sxs-lookup"><span data-stu-id="7a469-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="7a469-112">no A matriz de linhas nos documentos em que os pontos de sequência terminam.</span><span class="sxs-lookup"><span data-stu-id="7a469-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="7a469-113">no A matriz de colunas nos documentos em que os pontos de sequência terminam.</span><span class="sxs-lookup"><span data-stu-id="7a469-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a469-114">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="7a469-114">Return Value</span></span>  

 <span data-ttu-id="7a469-115">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="7a469-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a469-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a469-116">Requirements</span></span>  

 <span data-ttu-id="7a469-117">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7a469-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a469-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="7a469-118">See also</span></span>

- [<span data-ttu-id="7a469-119">Interface ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7a469-119">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
