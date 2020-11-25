---
title: Enumeração CorDebugIntercept
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 3d3d4af8e9ee073c0aefec418a3b53c4589adf0d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729103"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="6e3d8-102">Enumeração CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="6e3d8-102">CorDebugIntercept Enumeration</span></span>

<span data-ttu-id="6e3d8-103">Indica os tipos de código que podem ser interceptados (ou seja, percorridos).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e3d8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6e3d8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="6e3d8-105">Membros</span><span class="sxs-lookup"><span data-stu-id="6e3d8-105">Members</span></span>  
  
|<span data-ttu-id="6e3d8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6e3d8-106">Member</span></span>|<span data-ttu-id="6e3d8-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="6e3d8-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="6e3d8-108">Nenhum código pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="6e3d8-109">Um construtor pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="6e3d8-110">Um filtro de exceção pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="6e3d8-111">O código que impõe a segurança pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="6e3d8-112">Uma política de contexto pode ser interceptada.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="6e3d8-113">Não usado.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="6e3d8-114">Todo o código pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e3d8-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="6e3d8-115">Remarks</span></span>  

 <span data-ttu-id="6e3d8-116">Use o método [ICorDebugStepper:: SetInterceptMask](icordebugstepper-setinterceptmask-method.md) para estabelecer os tipos de código que podem ser interceptados.</span><span class="sxs-lookup"><span data-stu-id="6e3d8-116">Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e3d8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e3d8-117">Requirements</span></span>  

 <span data-ttu-id="6e3d8-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e3d8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e3d8-119">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e3d8-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e3d8-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e3d8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e3d8-121">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e3d8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3d8-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="6e3d8-122">See also</span></span>

- [<span data-ttu-id="6e3d8-123">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="6e3d8-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
