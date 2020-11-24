---
title: Método ICorDebugFrame::GetChain
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
ms.openlocfilehash: d605ac36c17a815bf546819e331830f51142cfcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690415"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="aa5b6-102">Método ICorDebugFrame::GetChain</span><span class="sxs-lookup"><span data-stu-id="aa5b6-102">ICorDebugFrame::GetChain Method</span></span>

<span data-ttu-id="aa5b6-103">Obtém um ponteiro para a cadeia em que este quadro faz parte.</span><span class="sxs-lookup"><span data-stu-id="aa5b6-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa5b6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="aa5b6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa5b6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="aa5b6-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="aa5b6-106">fora Um ponteiro para o endereço de um objeto ICorDebugChain que representa a cadeia que contém esse quadro.</span><span class="sxs-lookup"><span data-stu-id="aa5b6-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa5b6-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa5b6-107">Requirements</span></span>  

 <span data-ttu-id="aa5b6-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa5b6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa5b6-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa5b6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa5b6-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa5b6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa5b6-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa5b6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
