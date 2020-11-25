---
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 006c81e0339a00aac14fb4f83f2bc140990bd546
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732574"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="e2169-102">Método ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="e2169-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>

<span data-ttu-id="e2169-103">Notifica o [ICorDebug](icordebug-interface.md) de que o processo está em execução.</span><span class="sxs-lookup"><span data-stu-id="e2169-103">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2169-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e2169-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2169-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e2169-105">Parameters</span></span>  

 `change`  
 <span data-ttu-id="e2169-106">no Um membro da enumeração [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="e2169-106">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2169-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="e2169-107">Remarks</span></span>  

 <span data-ttu-id="e2169-108">O depurador chama esse método para notificar [ICorDebug](icordebug-interface.md) que o processo está em execução.</span><span class="sxs-lookup"><span data-stu-id="e2169-108">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2169-109">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e2169-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2169-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2169-110">Requirements</span></span>  

 <span data-ttu-id="e2169-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2169-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2169-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2169-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2169-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2169-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2169-114">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2169-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2169-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="e2169-115">See also</span></span>

- [<span data-ttu-id="e2169-116">Interface ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="e2169-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="e2169-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="e2169-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
