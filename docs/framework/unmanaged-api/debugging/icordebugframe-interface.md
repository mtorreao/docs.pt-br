---
title: Interface ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: bdc17e2c6c63deae1420fe738eac51153f6b368e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726334"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="5c1f7-102">Interface ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="5c1f7-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="5c1f7-103">Representa um quadro na pilha atual.</span><span class="sxs-lookup"><span data-stu-id="5c1f7-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c1f7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5c1f7-104">Methods</span></span>  
  
|<span data-ttu-id="5c1f7-105">Método</span><span class="sxs-lookup"><span data-stu-id="5c1f7-105">Method</span></span>|<span data-ttu-id="5c1f7-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="5c1f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c1f7-107">Método CreateStepper</span><span class="sxs-lookup"><span data-stu-id="5c1f7-107">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="5c1f7-108">Obtém um ICorDebugStepper para executar operações de depuração relativas a isso `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="5c1f7-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="5c1f7-109">Método GetCallee</span><span class="sxs-lookup"><span data-stu-id="5c1f7-109">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="5c1f7-110">Obtém um ponteiro para o `ICorDebugFrame` na cadeia atual que este quadro chamou ou retorna NULL se esse for o quadro interno na cadeia.</span><span class="sxs-lookup"><span data-stu-id="5c1f7-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="5c1f7-111">Método GetCaller</span><span class="sxs-lookup"><span data-stu-id="5c1f7-111">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="5c1f7-112">Obtém um ponteiro para o `ICorDebugFrame` na cadeia atual que chamou esse quadro ou retorna NULL se esse for o quadro mais externo na cadeia.</span><span class="sxs-lookup"><span data-stu-id="5c1f7-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="5c1f7-113">Método GetChain</span><span class="sxs-lookup"><span data-stu-id="5c1f7-113">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="5c1f7-114">Obtém um ponteiro para o ICorDebugChain que `ICorDebugFrame` faz parte de.</span><span class="sxs-lookup"><span data-stu-id="5c1f7-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="5c1f7-115">Método GetCode</span><span class="sxs-lookup"><span data-stu-id="5c1f7-115">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="5c1f7-116">Obtém um ponteiro para o ICorDebugCode associado a este quadro de pilhas.</span><span class="sxs-lookup"><span data-stu-id="5c1f7-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="5c1f7-117">Método GetFunction</span><span class="sxs-lookup"><span data-stu-id="5c1f7-117">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="5c1f7-118">Obtém um ponteiro para o ICorDebugFunction que contém o código associado a esse quadro de pilhas.</span><span class="sxs-lookup"><span data-stu-id="5c1f7-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="5c1f7-119">Método GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="5c1f7-119">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="5c1f7-120">Obtém o token de metadados para a função que contém o código associado a esse quadro de pilha.</span><span class="sxs-lookup"><span data-stu-id="5c1f7-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="5c1f7-121">Método GetStackRange</span><span class="sxs-lookup"><span data-stu-id="5c1f7-121">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="5c1f7-122">Obtém o intervalo de endereços absolutos do quadro de pilha representado por isso `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="5c1f7-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c1f7-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="5c1f7-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c1f7-124">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="5c1f7-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c1f7-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c1f7-125">Requirements</span></span>  

 <span data-ttu-id="5c1f7-126">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c1f7-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c1f7-127">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c1f7-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c1f7-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c1f7-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c1f7-129">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c1f7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1f7-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="5c1f7-130">See also</span></span>

- [<span data-ttu-id="5c1f7-131">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="5c1f7-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
