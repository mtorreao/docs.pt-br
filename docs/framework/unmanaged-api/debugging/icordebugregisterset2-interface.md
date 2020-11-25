---
title: Interface ICorDebugRegisterSet2
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: c04bb3a7584fcb783af929e87713dbec67ad705f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712309"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="e1d5c-102">Interface ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="e1d5c-102">ICorDebugRegisterSet2 Interface</span></span>

<span data-ttu-id="e1d5c-103">Estende os recursos da interface [ICorDebugRegisterSet](icordebugregisterset-interface.md) para plataformas de hardware que têm mais de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-103">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1d5c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e1d5c-104">Methods</span></span>  
  
|<span data-ttu-id="e1d5c-105">Método</span><span class="sxs-lookup"><span data-stu-id="e1d5c-105">Method</span></span>|<span data-ttu-id="e1d5c-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e1d5c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1d5c-107">Método GetRegisters</span><span class="sxs-lookup"><span data-stu-id="e1d5c-107">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="e1d5c-108">Obtém o valor de cada registro (no computador que está executando o código) que é especificado pela máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="e1d5c-109">Método GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="e1d5c-109">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="e1d5c-110">Obtém uma matriz de bytes que fornece um bitmap dos registros disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="e1d5c-111">Método SetRegisters</span><span class="sxs-lookup"><span data-stu-id="e1d5c-111">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="e1d5c-112">Não implementado na versão .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1d5c-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="e1d5c-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1d5c-114">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1d5c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1d5c-115">Requirements</span></span>  

 <span data-ttu-id="e1d5c-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1d5c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1d5c-117">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1d5c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1d5c-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1d5c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1d5c-119">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1d5c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d5c-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="e1d5c-120">See also</span></span>

- [<span data-ttu-id="e1d5c-121">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="e1d5c-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e1d5c-122">Interface ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="e1d5c-122">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
