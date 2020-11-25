---
title: Método ICorDebugStepper::SetInterceptMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: 814bf87039ef57056f13994af1b873f8f57c7804
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718209"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="024a9-102">Método ICorDebugStepper::SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="024a9-102">ICorDebugStepper::SetInterceptMask Method</span></span>

<span data-ttu-id="024a9-103">Define um valor que especifica os tipos de código que são percorridos.</span><span class="sxs-lookup"><span data-stu-id="024a9-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="024a9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="024a9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="024a9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="024a9-105">Parameters</span></span>  

 `mask`  
 <span data-ttu-id="024a9-106">no Uma combinação de valores da enumeração CorDebugIntercept que especifica os tipos de código.</span><span class="sxs-lookup"><span data-stu-id="024a9-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="024a9-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="024a9-107">Remarks</span></span>  

 <span data-ttu-id="024a9-108">Se o bit de um interceptor for definido, o stepper será concluído quando o tipo de código de interceptação for encontrado.</span><span class="sxs-lookup"><span data-stu-id="024a9-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="024a9-109">Se o bit for apagado, o código de interceptação será ignorado.</span><span class="sxs-lookup"><span data-stu-id="024a9-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="024a9-110">O `SetInterceptMask` método pode ter interações imprevistas com [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (do ponto de vista do usuário).</span><span class="sxs-lookup"><span data-stu-id="024a9-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="024a9-111">Por exemplo, se a única parte visível (ou seja, não interna) do código de inicialização da classe não tiver informações de mapeamento e STOP_NO_MAPPING_INFO não estiver definida (consulte o método [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) e a Enumeração CorDebugUnmappedStop), o stepper passará pela inicialização da classe.</span><span class="sxs-lookup"><span data-stu-id="024a9-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="024a9-112">Por padrão, somente o valor INTERCEPT_NONE da `CorDebugIntercept` Enumeração será usado.</span><span class="sxs-lookup"><span data-stu-id="024a9-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="024a9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="024a9-113">Requirements</span></span>  

 <span data-ttu-id="024a9-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="024a9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="024a9-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="024a9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="024a9-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="024a9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="024a9-117">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="024a9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
