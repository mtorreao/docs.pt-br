---
title: Interface ICorDebugValueBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: cf0a87afd1c0057c054205432fea7aa5844afb53
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684389"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="33656-102">Interface ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="33656-102">ICorDebugValueBreakpoint Interface</span></span>

<span data-ttu-id="33656-103">Estende a interface ICorDebugBreakpoint para fornecer acesso a valores específicos.</span><span class="sxs-lookup"><span data-stu-id="33656-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33656-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="33656-104">Methods</span></span>  
  
|<span data-ttu-id="33656-105">Método</span><span class="sxs-lookup"><span data-stu-id="33656-105">Method</span></span>|<span data-ttu-id="33656-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="33656-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33656-107">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="33656-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="33656-108">Obtém um ponteiro de interface para um objeto ICorDebugValue que representa o valor do objeto no qual o ponto de interrupção está definido.</span><span class="sxs-lookup"><span data-stu-id="33656-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33656-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="33656-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33656-110">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="33656-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33656-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33656-111">Requirements</span></span>  

 <span data-ttu-id="33656-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33656-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33656-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33656-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33656-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33656-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33656-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33656-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33656-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="33656-116">See also</span></span>

- [<span data-ttu-id="33656-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="33656-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
