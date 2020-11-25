---
title: Interface ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: e219c703ce2d8bb42f824a8892991f6803e6ef9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713724"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="2e250-102">Interface ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="2e250-102">ICorDebugDataTarget3 Interface</span></span>

<span data-ttu-id="2e250-103">Estende logicamente a interface [ICorDebugDataTarget](icordebugdatatarget-interface.md) para fornecer informações sobre os módulos carregados.</span><span class="sxs-lookup"><span data-stu-id="2e250-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="2e250-104">Método</span><span class="sxs-lookup"><span data-stu-id="2e250-104">Method</span></span>  
  
|<span data-ttu-id="2e250-105">Método</span><span class="sxs-lookup"><span data-stu-id="2e250-105">Method</span></span>|<span data-ttu-id="2e250-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2e250-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e250-107">Método GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="2e250-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="2e250-108">Obtém uma lista dos módulos que foram carregados até agora.</span><span class="sxs-lookup"><span data-stu-id="2e250-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e250-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="2e250-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e250-110">Essa interface está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2e250-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="2e250-111">Se você implementar essa interface para cenários ICorDebug fora do .NET Native, o Common Language Runtime ignorará essa interface.</span><span class="sxs-lookup"><span data-stu-id="2e250-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e250-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e250-112">Requirements</span></span>  

 <span data-ttu-id="2e250-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e250-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e250-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e250-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e250-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e250-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e250-116">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e250-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e250-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="2e250-117">See also</span></span>

- [<span data-ttu-id="2e250-118">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="2e250-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2e250-119">Depuração</span><span class="sxs-lookup"><span data-stu-id="2e250-119">Debugging</span></span>](index.md)
