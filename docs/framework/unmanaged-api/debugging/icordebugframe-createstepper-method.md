---
title: Método ICorDebugFrame::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 5dfb64d0c440cbd2c8a8a65b2c18d78f02a7615e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679709"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="20317-102">Método ICorDebugFrame::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="20317-102">ICorDebugFrame::CreateStepper Method</span></span>

<span data-ttu-id="20317-103">Obtém um stepper que permite que o depurador execute operações de depuração relativas a esse ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="20317-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20317-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="20317-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20317-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="20317-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="20317-106">fora Um ponteiro para o endereço de um objeto ICorDebugStepper que permite que o depurador execute operações de depuração relativas ao quadro atual.</span><span class="sxs-lookup"><span data-stu-id="20317-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20317-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="20317-107">Remarks</span></span>  

 <span data-ttu-id="20317-108">Se o quadro não estiver ativo, o objeto stepper normalmente precisará retornar ao quadro antes da conclusão da etapa.</span><span class="sxs-lookup"><span data-stu-id="20317-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20317-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20317-109">Requirements</span></span>  

 <span data-ttu-id="20317-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20317-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20317-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20317-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20317-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20317-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20317-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20317-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
