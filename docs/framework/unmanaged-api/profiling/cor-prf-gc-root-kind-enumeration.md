---
title: Enumeração COR_PRF_GC_ROOT_KIND
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
ms.openlocfilehash: e86074031b8fc2c82636e7aef2177eaf04a9db14
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682356"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a><span data-ttu-id="63d1f-102">Enumeração COR_PRF_GC_ROOT_KIND</span><span class="sxs-lookup"><span data-stu-id="63d1f-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>

<span data-ttu-id="63d1f-103">Indica o tipo de raiz de coleta de lixo que é exposta pelo retorno de chamada [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="63d1f-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d1f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="63d1f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="63d1f-105">Membros</span><span class="sxs-lookup"><span data-stu-id="63d1f-105">Members</span></span>  
  
|<span data-ttu-id="63d1f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="63d1f-106">Member</span></span>|<span data-ttu-id="63d1f-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="63d1f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="63d1f-108">A raiz é uma variável na pilha.</span><span class="sxs-lookup"><span data-stu-id="63d1f-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="63d1f-109">A raiz é uma entrada na fila do finalizador.</span><span class="sxs-lookup"><span data-stu-id="63d1f-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="63d1f-110">A raiz é um identificador de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="63d1f-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="63d1f-111">O tipo de raiz não está especificado.</span><span class="sxs-lookup"><span data-stu-id="63d1f-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63d1f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63d1f-112">Requirements</span></span>  

 <span data-ttu-id="63d1f-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d1f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d1f-114">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="63d1f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63d1f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d1f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d1f-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d1f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d1f-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="63d1f-117">See also</span></span>

- [<span data-ttu-id="63d1f-118">Criando perfil de enumerações</span><span class="sxs-lookup"><span data-stu-id="63d1f-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
