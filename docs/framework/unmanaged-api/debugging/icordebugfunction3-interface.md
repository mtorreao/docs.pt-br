---
title: Interface ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 17eda7470e5f2e4b41d1f2ed164843eaeeedea93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695863"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="037c8-102">Interface ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="037c8-102">ICorDebugFunction3 Interface</span></span>

<span data-ttu-id="037c8-103">[Com suporte no .NET Framework 4.5.2 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="037c8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="037c8-104">Estende a interface de ICorDebugFunction logicamente para fornecer acesso ao código a partir de uma solicitação ReJIT.</span><span class="sxs-lookup"><span data-stu-id="037c8-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="037c8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="037c8-105">Methods</span></span>  
  
|<span data-ttu-id="037c8-106">Método</span><span class="sxs-lookup"><span data-stu-id="037c8-106">Method</span></span>|<span data-ttu-id="037c8-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="037c8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="037c8-108">Método GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="037c8-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="037c8-109">Obtém um ponteiro de interface para um [ICorDebugILCode](icordebugilcode-interface.md) que contém o Il de uma solicitação de ReJIT ativa.</span><span class="sxs-lookup"><span data-stu-id="037c8-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="037c8-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="037c8-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="037c8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="037c8-111">Requirements</span></span>  

 <span data-ttu-id="037c8-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="037c8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="037c8-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="037c8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="037c8-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="037c8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="037c8-115">**.NET Framework versões:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="037c8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037c8-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="037c8-116">See also</span></span>

- [<span data-ttu-id="037c8-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="037c8-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="037c8-118">Depuração</span><span class="sxs-lookup"><span data-stu-id="037c8-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="037c8-119">ReJIT: um guia de How-To</span><span class="sxs-lookup"><span data-stu-id="037c8-119">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
