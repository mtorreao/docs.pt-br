---
title: Método ICorDebugChain::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: daecd216b4d7e9c23336b8956c13735549be901b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730130"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="fc171-102">Método ICorDebugChain::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="fc171-102">ICorDebugChain::GetActiveFrame Method</span></span>

<span data-ttu-id="fc171-103">Obtém o quadro ativo (ou seja, mais recente) na cadeia.</span><span class="sxs-lookup"><span data-stu-id="fc171-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc171-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fc171-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc171-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fc171-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="fc171-106">fora Um ponteiro para o endereço de um objeto ICorDebugFrame que representa o quadro ativo (ou seja, mais recente) na cadeia.</span><span class="sxs-lookup"><span data-stu-id="fc171-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc171-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="fc171-107">Remarks</span></span>  

 <span data-ttu-id="fc171-108">Se nenhum quadro de pilha gerenciado estiver disponível, `ppFrame` será definido como nulo.</span><span class="sxs-lookup"><span data-stu-id="fc171-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="fc171-109">Se o quadro ativo não estiver disponível, a chamada terá sucesso e `ppFrame` será NULL.</span><span class="sxs-lookup"><span data-stu-id="fc171-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="fc171-110">Os quadros ativos não estarão disponíveis para cadeias iniciadas devido a CHAIN_ENTER_UNMANAGED e para algumas cadeias iniciadas devido a CHAIN_CLASS_INIT.</span><span class="sxs-lookup"><span data-stu-id="fc171-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="fc171-111">Consulte a enumeração CorDebugChainReason.</span><span class="sxs-lookup"><span data-stu-id="fc171-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc171-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc171-112">Requirements</span></span>  

 <span data-ttu-id="fc171-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc171-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc171-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc171-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc171-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc171-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc171-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc171-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
