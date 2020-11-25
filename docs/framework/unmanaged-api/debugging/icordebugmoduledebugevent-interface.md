---
title: Interface ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 62d419a193cff000e1dd748d0cbb6b61775a81aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695810"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="195b6-102">Interface ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="195b6-102">ICorDebugModuleDebugEvent Interface</span></span>

<span data-ttu-id="195b6-103">Estende a interface [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para dar suporte a eventos no nível do módulo.</span><span class="sxs-lookup"><span data-stu-id="195b6-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="195b6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="195b6-104">Methods</span></span>  
  
|<span data-ttu-id="195b6-105">Método</span><span class="sxs-lookup"><span data-stu-id="195b6-105">Method</span></span>|<span data-ttu-id="195b6-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="195b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="195b6-107">Método GetModule</span><span class="sxs-lookup"><span data-stu-id="195b6-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="195b6-108">Obtém o módulo mesclado que acabou de ser carregado ou descarregado.</span><span class="sxs-lookup"><span data-stu-id="195b6-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="195b6-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="195b6-109">Remarks</span></span>  

 <span data-ttu-id="195b6-110">Os tipos de evento [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) e [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementam essa interface.</span><span class="sxs-lookup"><span data-stu-id="195b6-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="195b6-111">A interface está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="195b6-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="195b6-112">A tentativa de chamar `QueryInterface` para recuperar um ponteiro de interface retorna `E_NOINTERFACE` para cenários ICorDebug fora do .net Native.</span><span class="sxs-lookup"><span data-stu-id="195b6-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="195b6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="195b6-113">Requirements</span></span>  

 <span data-ttu-id="195b6-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195b6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195b6-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="195b6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="195b6-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="195b6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="195b6-117">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195b6-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195b6-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="195b6-118">See also</span></span>

- [<span data-ttu-id="195b6-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="195b6-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="195b6-120">Depuração</span><span class="sxs-lookup"><span data-stu-id="195b6-120">Debugging</span></span>](index.md)
