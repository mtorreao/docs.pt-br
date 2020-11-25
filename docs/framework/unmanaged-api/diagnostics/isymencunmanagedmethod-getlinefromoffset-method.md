---
title: Método ISymENCUnmanagedMethod::GetLineFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 196993df9058d3eb8167e0144255c5fe366c54f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707354"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="cc2d9-102">Método ISymENCUnmanagedMethod::GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="cc2d9-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>

<span data-ttu-id="cc2d9-103">Obtém as informações de linha associadas a um deslocamento.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="cc2d9-104">Se o parâmetro offset ( `dwOffset` ) não for um ponto de sequência, esse método obterá as informações de linha associadas ao deslocamento anterior.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc2d9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc2d9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc2d9-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cc2d9-106">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="cc2d9-107">no Um `ULONG32` que contém o deslocamento.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="cc2d9-108">fora Um ponteiro para um `ULONG32` que recebe a linha.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="cc2d9-109">fora Um ponteiro para um `ULONG32` que recebe a coluna.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="cc2d9-110">fora Um ponteiro para um `ULONG32` que recebe a linha final.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="cc2d9-111">fora Um ponteiro para um `ULONG32` que recebe a coluna final.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="cc2d9-112">fora Um ponteiro para um `ULONG32` que recebe o ponto de sequência associado.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc2d9-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="cc2d9-113">Return Value</span></span>  

 <span data-ttu-id="cc2d9-114">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="cc2d9-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc2d9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc2d9-115">Requirements</span></span>  

 <span data-ttu-id="cc2d9-116">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cc2d9-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc2d9-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc2d9-117">See also</span></span>

- [<span data-ttu-id="cc2d9-118">Interface ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="cc2d9-118">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
