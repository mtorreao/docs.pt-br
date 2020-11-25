---
title: Método ICorDebugStepper::SetUnmappedStopMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: 50fad8b38a6b33d0ddbb2f0f20676296c3d66737
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698722"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="c3395-102">Método ICorDebugStepper::SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="c3395-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>

<span data-ttu-id="c3395-103">Define um valor que especifica o tipo de código não mapeado no qual a execução será interrompida.</span><span class="sxs-lookup"><span data-stu-id="c3395-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3395-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c3395-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3395-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c3395-105">Parameters</span></span>  

 `mask`  
 <span data-ttu-id="c3395-106">no Um valor da Enumeração CorDebugUnmappedStop que especifica o tipo de código não mapeado no qual o depurador irá parar a execução.</span><span class="sxs-lookup"><span data-stu-id="c3395-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="c3395-107">O valor padrão é STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="c3395-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="c3395-108">O valor STOP_UNMANAGED é válido somente com depuração de interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="c3395-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3395-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="c3395-109">Remarks</span></span>  

 <span data-ttu-id="c3395-110">Quando o depurador encontra uma compilação JIT (just-in-time) que não tem mapeamento correspondente à MSIL (Microsoft Intermediate Language), ele interrompe a execução se o sinalizador que especifica esse tipo de código não mapeado tiver sido definido; caso contrário, a etapa continuará de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="c3395-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="c3395-111">Se o depurador não usar um stepper para inserir um método, ele não irá necessariamente passar por código não mapeado.</span><span class="sxs-lookup"><span data-stu-id="c3395-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3395-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3395-112">Requirements</span></span>  

 <span data-ttu-id="c3395-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3395-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3395-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3395-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3395-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3395-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3395-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3395-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
