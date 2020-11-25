---
title: Método ISymUnmanagedWriter3::OpenMethod2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: 39235c5c26cb168dfc995de97f72b80dccb6b818
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720289"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="39410-102">Método ISymUnmanagedWriter3::OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="39410-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>

<span data-ttu-id="39410-103">Abre um método e fornece seu deslocamento de seção real na imagem.</span><span class="sxs-lookup"><span data-stu-id="39410-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39410-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="39410-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39410-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="39410-105">Parameters</span></span>  

 `method`  
 <span data-ttu-id="39410-106">no O token de metadados para o método a ser aberto.</span><span class="sxs-lookup"><span data-stu-id="39410-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="39410-107">no O deslocamento da seção na imagem.</span><span class="sxs-lookup"><span data-stu-id="39410-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="39410-108">no O deslocamento na imagem.</span><span class="sxs-lookup"><span data-stu-id="39410-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39410-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="39410-109">Return Value</span></span>  

 <span data-ttu-id="39410-110">S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.</span><span class="sxs-lookup"><span data-stu-id="39410-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39410-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39410-111">Requirements</span></span>  

 <span data-ttu-id="39410-112">**Cabeçalho:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="39410-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39410-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="39410-113">See also</span></span>

- [<span data-ttu-id="39410-114">Interface ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="39410-114">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="39410-115">Método OpenMethod</span><span class="sxs-lookup"><span data-stu-id="39410-115">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
