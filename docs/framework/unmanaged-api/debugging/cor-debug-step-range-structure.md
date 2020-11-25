---
title: Estrutura COR_DEBUG_STEP_RANGE
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
ms.openlocfilehash: cd85ba2e6a907ff9546614e02b4da5f45e74b924
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726633"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="8a5ca-102">Estrutura COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="8a5ca-102">COR_DEBUG_STEP_RANGE Structure</span></span>

<span data-ttu-id="8a5ca-103">Contém as informações de deslocamento para um intervalo de código.</span><span class="sxs-lookup"><span data-stu-id="8a5ca-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="8a5ca-104">Essa estrutura é usada pelo método [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a5ca-104">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a5ca-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8a5ca-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="8a5ca-106">Membros</span><span class="sxs-lookup"><span data-stu-id="8a5ca-106">Members</span></span>  
  
|<span data-ttu-id="8a5ca-107">Membro</span><span class="sxs-lookup"><span data-stu-id="8a5ca-107">Member</span></span>|<span data-ttu-id="8a5ca-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8a5ca-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="8a5ca-109">O deslocamento do início do intervalo.</span><span class="sxs-lookup"><span data-stu-id="8a5ca-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="8a5ca-110">O deslocamento do final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="8a5ca-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a5ca-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a5ca-111">Requirements</span></span>  

 <span data-ttu-id="8a5ca-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a5ca-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a5ca-113">**Cabeçalho:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="8a5ca-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="8a5ca-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a5ca-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a5ca-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a5ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a5ca-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a5ca-116">See also</span></span>

- [<span data-ttu-id="8a5ca-117">Método StepRange</span><span class="sxs-lookup"><span data-stu-id="8a5ca-117">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="8a5ca-118">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="8a5ca-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="8a5ca-119">Depuração</span><span class="sxs-lookup"><span data-stu-id="8a5ca-119">Debugging</span></span>](index.md)
