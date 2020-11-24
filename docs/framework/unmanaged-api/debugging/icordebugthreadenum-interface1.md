---
title: Interface ICorDebugThreadEnum
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
ms.openlocfilehash: ca7668f23671721477c561774bab03279c4c18c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678544"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="4bd7b-102">Interface ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="4bd7b-102">ICorDebugThreadEnum Interface</span></span>

<span data-ttu-id="4bd7b-103">Implementa métodos ICorDebugEnum e enumera matrizes ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="4bd7b-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4bd7b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4bd7b-104">Methods</span></span>  
  
|<span data-ttu-id="4bd7b-105">Método</span><span class="sxs-lookup"><span data-stu-id="4bd7b-105">Method</span></span>|<span data-ttu-id="4bd7b-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4bd7b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4bd7b-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="4bd7b-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="4bd7b-108">Obtém o número especificado de `ICorDebugThread` instâncias da enumeração, começando na posição atual.</span><span class="sxs-lookup"><span data-stu-id="4bd7b-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bd7b-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="4bd7b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4bd7b-110">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="4bd7b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd7b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4bd7b-111">Requirements</span></span>  

 <span data-ttu-id="4bd7b-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bd7b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bd7b-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bd7b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bd7b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bd7b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bd7b-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd7b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd7b-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="4bd7b-116">See also</span></span>

- [<span data-ttu-id="4bd7b-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="4bd7b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
