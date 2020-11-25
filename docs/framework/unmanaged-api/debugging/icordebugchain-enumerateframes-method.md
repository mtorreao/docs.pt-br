---
title: Método ICorDebugChain::EnumerateFrames
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: ae6d81e6fdab0f8e3346d8a08a3b5ebc329a542a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730143"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="237e6-102">Método ICorDebugChain::EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="237e6-102">ICorDebugChain::EnumerateFrames Method</span></span>

<span data-ttu-id="237e6-103">Obtém um enumerador que contém todos os quadros de pilha gerenciados na cadeia, começando com o quadro mais recente.</span><span class="sxs-lookup"><span data-stu-id="237e6-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="237e6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="237e6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="237e6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="237e6-105">Parameters</span></span>  

 `ppFrames`  
 <span data-ttu-id="237e6-106">fora Um ponteiro para o endereço de um objeto ICorDebugFrameEnum que é o enumerador para os quadros de pilha.</span><span class="sxs-lookup"><span data-stu-id="237e6-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="237e6-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="237e6-107">Remarks</span></span>  

 <span data-ttu-id="237e6-108">A cadeia representa a pilha de chamadas física para o thread.</span><span class="sxs-lookup"><span data-stu-id="237e6-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="237e6-109">O `EnumerateFrames` método deve ser chamado somente para cadeias gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="237e6-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="237e6-110">A API de depuração não fornece métodos para obter quadros contidos em cadeias não gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="237e6-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="237e6-111">O depurador deve usar outros meios para obter essas informações.</span><span class="sxs-lookup"><span data-stu-id="237e6-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="237e6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="237e6-112">Requirements</span></span>  

 <span data-ttu-id="237e6-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="237e6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="237e6-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="237e6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="237e6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="237e6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="237e6-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="237e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
