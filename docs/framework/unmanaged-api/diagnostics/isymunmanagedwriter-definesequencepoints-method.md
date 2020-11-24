---
title: Método ISymUnmanagedWriter::DefineSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
ms.openlocfilehash: af8beb1ec627b93faeb7329a03579319ca3880ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678318"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="f62ab-102">Método ISymUnmanagedWriter::DefineSequencePoints</span><span class="sxs-lookup"><span data-stu-id="f62ab-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>

<span data-ttu-id="f62ab-103">Define um grupo de pontos de sequência dentro do método atual.</span><span class="sxs-lookup"><span data-stu-id="f62ab-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="f62ab-104">Cada linha inicial e coluna inicial definem o início de uma instrução dentro de um método.</span><span class="sxs-lookup"><span data-stu-id="f62ab-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="f62ab-105">Cada linha final e coluna final definem o final de uma instrução dentro de um método.</span><span class="sxs-lookup"><span data-stu-id="f62ab-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="f62ab-106">As matrizes devem ser classificadas em ordem crescente de deslocamentos.</span><span class="sxs-lookup"><span data-stu-id="f62ab-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="f62ab-107">O deslocamento é sempre medido a partir do início do método, em bytes.</span><span class="sxs-lookup"><span data-stu-id="f62ab-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f62ab-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f62ab-108">Syntax</span></span>  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f62ab-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f62ab-109">Parameters</span></span>  

 `document`  
 <span data-ttu-id="f62ab-110">no O objeto de documento para o qual os pontos de sequência estão sendo definidos.</span><span class="sxs-lookup"><span data-stu-id="f62ab-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="f62ab-111">no Um `ULONG32` que indica o tamanho de cada um dos `offsets` buffers,,, `lines` `columns` `endLines` e `endColumns` .</span><span class="sxs-lookup"><span data-stu-id="f62ab-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="f62ab-112">no O deslocamento dos pontos de sequência medidos a partir do início do método.</span><span class="sxs-lookup"><span data-stu-id="f62ab-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="f62ab-113">no Os números de linha inicial dos pontos de sequência.</span><span class="sxs-lookup"><span data-stu-id="f62ab-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="f62ab-114">no Os números de coluna inicial dos pontos de sequência.</span><span class="sxs-lookup"><span data-stu-id="f62ab-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="f62ab-115">no Os números de linha final dos pontos de sequência.</span><span class="sxs-lookup"><span data-stu-id="f62ab-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="f62ab-116">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="f62ab-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="f62ab-117">no Os números de coluna final dos pontos de sequência.</span><span class="sxs-lookup"><span data-stu-id="f62ab-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="f62ab-118">Esse parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="f62ab-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f62ab-119">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f62ab-119">Return Value</span></span>  

 <span data-ttu-id="f62ab-120">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="f62ab-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f62ab-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f62ab-121">Requirements</span></span>  

 <span data-ttu-id="f62ab-122">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f62ab-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f62ab-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="f62ab-123">See also</span></span>

- [<span data-ttu-id="f62ab-124">Interface ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f62ab-124">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
