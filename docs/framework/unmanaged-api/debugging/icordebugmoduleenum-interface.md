---
title: Interface ICorDebugModuleEnum
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: 08d16393a04888cd3f1a03fa209a1fceac28520b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724735"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="c5bc8-102">Interface ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="c5bc8-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="c5bc8-103">Implementa métodos ICorDebugEnum e enumera matrizes ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="c5bc8-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5bc8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c5bc8-104">Methods</span></span>  
  
|<span data-ttu-id="c5bc8-105">Método</span><span class="sxs-lookup"><span data-stu-id="c5bc8-105">Method</span></span>|<span data-ttu-id="c5bc8-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c5bc8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5bc8-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="c5bc8-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="c5bc8-108">Obtém o número especificado de `ICorDebugModule` instâncias da enumeração, começando na posição atual.</span><span class="sxs-lookup"><span data-stu-id="c5bc8-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5bc8-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="c5bc8-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5bc8-110">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="c5bc8-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5bc8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5bc8-111">Requirements</span></span>  

 <span data-ttu-id="c5bc8-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5bc8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5bc8-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5bc8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5bc8-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5bc8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5bc8-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5bc8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bc8-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="c5bc8-116">See also</span></span>

- [<span data-ttu-id="c5bc8-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="c5bc8-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
