---
title: Método ICorDebugChain::GetReason
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
ms.openlocfilehash: 58e40995012d98c1af6a41eb12d898c6b9b1d47b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719665"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="1357c-102">Método ICorDebugChain::GetReason</span><span class="sxs-lookup"><span data-stu-id="1357c-102">ICorDebugChain::GetReason Method</span></span>

<span data-ttu-id="1357c-103">Obtém o motivo do Genesis desta cadeia de chamada.</span><span class="sxs-lookup"><span data-stu-id="1357c-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1357c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1357c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1357c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1357c-105">Parameters</span></span>  

 `pReason`  
 <span data-ttu-id="1357c-106">fora Um ponteiro para um valor (uma combinação bit-a-ponto) da enumeração CorDebugChainReason que indica o motivo do Genesis desta cadeia de chamada.</span><span class="sxs-lookup"><span data-stu-id="1357c-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1357c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1357c-107">Requirements</span></span>  

 <span data-ttu-id="1357c-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1357c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1357c-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1357c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1357c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1357c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1357c-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1357c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
