---
title: Método ICorDebugChain::GetPrevious
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
ms.openlocfilehash: 326e170fa98c9e365f9b68bedb585f547ca207ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727699"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="58d7b-102">Método ICorDebugChain::GetPrevious</span><span class="sxs-lookup"><span data-stu-id="58d7b-102">ICorDebugChain::GetPrevious Method</span></span>

<span data-ttu-id="58d7b-103">Obtém a cadeia de quadros anterior para o thread.</span><span class="sxs-lookup"><span data-stu-id="58d7b-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d7b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="58d7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58d7b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="58d7b-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="58d7b-106">fora Um ponteiro para o endereço de um objeto ICorDebugChain que representa a cadeia de quadros anterior para esse thread.</span><span class="sxs-lookup"><span data-stu-id="58d7b-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="58d7b-107">Se essa cadeia for a primeira cadeia, `ppChain` será NULL.</span><span class="sxs-lookup"><span data-stu-id="58d7b-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58d7b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58d7b-108">Requirements</span></span>  

 <span data-ttu-id="58d7b-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58d7b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d7b-110">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58d7b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58d7b-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58d7b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58d7b-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d7b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
