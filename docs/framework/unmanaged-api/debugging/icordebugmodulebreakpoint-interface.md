---
title: Interface ICorDebugModuleBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
ms.openlocfilehash: 14f2b6822744070e649cf9a6722272992c0bf1c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709512"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="392b6-102">Interface ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="392b6-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="392b6-103">Fornece acesso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="392b6-103">Provides access to specific modules.</span></span> <span data-ttu-id="392b6-104">Essa interface é uma subclasse da interface ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="392b6-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="392b6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="392b6-105">Methods</span></span>  
  
|<span data-ttu-id="392b6-106">Método</span><span class="sxs-lookup"><span data-stu-id="392b6-106">Method</span></span>|<span data-ttu-id="392b6-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="392b6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="392b6-108">Método GetModule</span><span class="sxs-lookup"><span data-stu-id="392b6-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="392b6-109">Obtém um ponteiro de interface para um ICorDebugModule que faz referência ao módulo em que esse ponto de interrupção está definido.</span><span class="sxs-lookup"><span data-stu-id="392b6-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="392b6-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="392b6-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="392b6-111">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="392b6-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="392b6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="392b6-112">Requirements</span></span>  

 <span data-ttu-id="392b6-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="392b6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="392b6-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="392b6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="392b6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="392b6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="392b6-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="392b6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="392b6-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="392b6-117">See also</span></span>

- [<span data-ttu-id="392b6-118">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="392b6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
