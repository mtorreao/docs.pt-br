---
title: Método ICorDebugEval::Abort
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: 6e6ea5e42c5e1b1943a080ae02e1dbf6d702bebc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705846"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="268e4-102">Método ICorDebugEval::Abort</span><span class="sxs-lookup"><span data-stu-id="268e4-102">ICorDebugEval::Abort Method</span></span>

<span data-ttu-id="268e4-103">Anula a computação que esse objeto ICorDebugEval está executando no momento.</span><span class="sxs-lookup"><span data-stu-id="268e4-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="268e4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="268e4-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="268e4-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="268e4-105">Remarks</span></span>  

 <span data-ttu-id="268e4-106">Se a avaliação estiver aninhada e não for a mais recente, o `Abort` método poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="268e4-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="268e4-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="268e4-107">Requirements</span></span>  

 <span data-ttu-id="268e4-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="268e4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="268e4-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="268e4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="268e4-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="268e4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="268e4-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="268e4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
