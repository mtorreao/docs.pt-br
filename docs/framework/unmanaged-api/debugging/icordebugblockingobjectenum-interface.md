---
title: Interface ICorDebugBlockingObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: 221acf9bea714728a81b9f15c8165c1f9eba16a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719197"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="27485-102">Interface ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="27485-102">ICorDebugBlockingObjectEnum Interface</span></span>

<span data-ttu-id="27485-103">Fornece um enumerador para uma lista de estruturas [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="27485-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="27485-104">Essa interface é uma subclasse da interface ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="27485-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27485-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="27485-105">Methods</span></span>  
  
|<span data-ttu-id="27485-106">Método</span><span class="sxs-lookup"><span data-stu-id="27485-106">Method</span></span>|<span data-ttu-id="27485-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="27485-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27485-108">Método Next</span><span class="sxs-lookup"><span data-stu-id="27485-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="27485-109">Enumera por meio de uma lista de estruturas [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="27485-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27485-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="27485-110">Remarks</span></span>  

 <span data-ttu-id="27485-111">Cada `CorDebugBlockingObject` estrutura representa um objeto que está bloqueando um thread.</span><span class="sxs-lookup"><span data-stu-id="27485-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27485-112">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="27485-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27485-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27485-113">Requirements</span></span>  

 <span data-ttu-id="27485-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27485-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27485-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27485-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27485-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27485-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27485-117">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27485-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27485-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="27485-118">See also</span></span>

- [<span data-ttu-id="27485-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="27485-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="27485-120">Depuração</span><span class="sxs-lookup"><span data-stu-id="27485-120">Debugging</span></span>](index.md)
