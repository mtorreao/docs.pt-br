---
title: Método ICorDebugNativeFrame::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: 945a398d32b50efc81ba45e705ed9d4161ed1524
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709265"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="1f55c-102">Método ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="1f55c-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>

<span data-ttu-id="1f55c-103">Obtém o conjunto de registros para este quadro de pilhas.</span><span class="sxs-lookup"><span data-stu-id="1f55c-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f55c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1f55c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f55c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1f55c-105">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="1f55c-106">fora Um ponteiro para o endereço de um objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa o conjunto de registros para esse quadro de pilhas.</span><span class="sxs-lookup"><span data-stu-id="1f55c-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f55c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f55c-107">Requirements</span></span>  

 <span data-ttu-id="1f55c-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f55c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f55c-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f55c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f55c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f55c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f55c-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f55c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f55c-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="1f55c-112">See also</span></span>
