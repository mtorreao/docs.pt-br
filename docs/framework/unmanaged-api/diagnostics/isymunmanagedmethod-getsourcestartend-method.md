---
title: Método ISymUnmanagedMethod::GetSourceStartEnd
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: f53afa5f87f1502f287b25e3d9756f9a54ad6869
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699281"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="11149-102">Método ISymUnmanagedMethod::GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="11149-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>

<span data-ttu-id="11149-103">Obtém as posições do documento inicial e final da origem deste método.</span><span class="sxs-lookup"><span data-stu-id="11149-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="11149-104">A primeira posição da matriz é o início e a segunda posição da matriz é o final.</span><span class="sxs-lookup"><span data-stu-id="11149-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11149-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="11149-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11149-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="11149-106">Parameters</span></span>  

 `docs`  
 <span data-ttu-id="11149-107">no Os documentos de origem inicial e final.</span><span class="sxs-lookup"><span data-stu-id="11149-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="11149-108">no As linhas inicial e final nos documentos de origem correspondentes.</span><span class="sxs-lookup"><span data-stu-id="11149-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="11149-109">no As colunas inicial e final nos documentos de origem correspondentes.</span><span class="sxs-lookup"><span data-stu-id="11149-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="11149-110">[fora] `true` Se as posições foram definidas; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="11149-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11149-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="11149-111">Return Value</span></span>  

 <span data-ttu-id="11149-112">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="11149-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11149-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11149-113">Requirements</span></span>  

 <span data-ttu-id="11149-114">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="11149-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11149-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="11149-115">See also</span></span>

- [<span data-ttu-id="11149-116">Interface ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="11149-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
