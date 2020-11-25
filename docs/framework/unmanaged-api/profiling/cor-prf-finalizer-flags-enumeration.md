---
title: Enumeração COR_PRF_FINALIZER_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
ms.openlocfilehash: 2b766715d6d87ab17a7cdabf721bbebf67e1ff13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718573"
---
# <a name="cor_prf_finalizer_flags-enumeration"></a><span data-ttu-id="bf7f4-102">Enumeração COR_PRF_FINALIZER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bf7f4-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>

<span data-ttu-id="bf7f4-103">Descreve o finalizador de um objeto.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf7f4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bf7f4-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bf7f4-105">Membros</span><span class="sxs-lookup"><span data-stu-id="bf7f4-105">Members</span></span>  
  
|<span data-ttu-id="bf7f4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bf7f4-106">Member</span></span>|<span data-ttu-id="bf7f4-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="bf7f4-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="bf7f4-108">O finalizador é crítico.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf7f4-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="bf7f4-109">Remarks</span></span>  

 <span data-ttu-id="bf7f4-110">A `COR_PRF_FINALIZER_FLAGS` enumeração é usada pelo método [ICorProfilerCallback2:: FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) para descrever o finalizador de um objeto.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf7f4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf7f4-111">Requirements</span></span>  

 <span data-ttu-id="bf7f4-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf7f4-113">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="bf7f4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf7f4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf7f4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf7f4-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf7f4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7f4-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="bf7f4-116">See also</span></span>

- [<span data-ttu-id="bf7f4-117">Criando perfil de enumerações</span><span class="sxs-lookup"><span data-stu-id="bf7f4-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
