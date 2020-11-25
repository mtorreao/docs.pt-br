---
title: Interface ICorDebugInternalFrame
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
ms.openlocfilehash: b7e738f06f9a9a06caedec2bdd0de4ab57f6d9b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719717"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="63c20-102">Interface ICorDebugInternalFrame</span><span class="sxs-lookup"><span data-stu-id="63c20-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="63c20-103">Representa um quadro interno de tempo de execução na pilha.</span><span class="sxs-lookup"><span data-stu-id="63c20-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="63c20-104">Essa interface é uma subclasse da interface ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="63c20-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63c20-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="63c20-105">Methods</span></span>  
  
|<span data-ttu-id="63c20-106">Método</span><span class="sxs-lookup"><span data-stu-id="63c20-106">Method</span></span>|<span data-ttu-id="63c20-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="63c20-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63c20-108">Método GetFrameType</span><span class="sxs-lookup"><span data-stu-id="63c20-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="63c20-109">Obtém o tipo deste quadro interno.</span><span class="sxs-lookup"><span data-stu-id="63c20-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63c20-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="63c20-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63c20-111">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="63c20-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63c20-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63c20-112">Requirements</span></span>  

 <span data-ttu-id="63c20-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63c20-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63c20-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63c20-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63c20-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63c20-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63c20-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63c20-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c20-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="63c20-117">See also</span></span>

- [<span data-ttu-id="63c20-118">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="63c20-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
