---
title: Enumeração COR_PRF_MISC
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: 5a3c820b52ae9376d769ea9956edc0b8553a1f88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682166"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="8c188-102">Enumeração COR_PRF_MISC</span><span class="sxs-lookup"><span data-stu-id="8c188-102">COR_PRF_MISC Enumeration</span></span>

<span data-ttu-id="8c188-103">Contém valores constantes que especificam identificadores especiais.</span><span class="sxs-lookup"><span data-stu-id="8c188-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c188-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8c188-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="8c188-105">Membros</span><span class="sxs-lookup"><span data-stu-id="8c188-105">Members</span></span>  
  
|<span data-ttu-id="8c188-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8c188-106">Member</span></span>|<span data-ttu-id="8c188-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8c188-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="8c188-108">O identificador padrão usado por [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) para um módulo que ainda não foi anexado a um assembly.</span><span class="sxs-lookup"><span data-stu-id="8c188-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="8c188-109">O identificador de classe padrão para constantes globais que não pertencem a uma classe.</span><span class="sxs-lookup"><span data-stu-id="8c188-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="8c188-110">O identificador de módulo padrão para objetos globais que não pertencem a um módulo.</span><span class="sxs-lookup"><span data-stu-id="8c188-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c188-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c188-111">Requirements</span></span>  

 <span data-ttu-id="8c188-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c188-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c188-113">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="8c188-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c188-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c188-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c188-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c188-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c188-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c188-116">See also</span></span>

- [<span data-ttu-id="8c188-117">Criando perfil de enumerações</span><span class="sxs-lookup"><span data-stu-id="8c188-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
