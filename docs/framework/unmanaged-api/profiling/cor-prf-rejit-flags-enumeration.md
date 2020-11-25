---
title: Enumeração COR_PRF_REJIT_FLAGS
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 09349674e0cf80649cc948e25a1c476c6f8097e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716363"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="6df54-102">Enumeração COR_PRF_REJIT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6df54-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>

<span data-ttu-id="6df54-103">Contém valores que indicam como a API [ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) deve se comportar.</span><span class="sxs-lookup"><span data-stu-id="6df54-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6df54-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6df54-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6df54-105">Membros</span><span class="sxs-lookup"><span data-stu-id="6df54-105">Members</span></span>  
  
|<span data-ttu-id="6df54-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6df54-106">Member</span></span>|<span data-ttu-id="6df54-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="6df54-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="6df54-108">Os métodos ReJITted serão impedidos de serem embutidos em outros métodos.</span><span class="sxs-lookup"><span data-stu-id="6df54-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="6df54-109">Receber `GetFunctionParameters` retornos de chamada para todos os métodos que embutiram os métodos solicitados a serem ReJITteddos.</span><span class="sxs-lookup"><span data-stu-id="6df54-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="6df54-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6df54-110">Requirements</span></span>  

 <span data-ttu-id="6df54-111">**Plataformas:** Consulte [sistemas operacionais com suporte do .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="6df54-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="6df54-112">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="6df54-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6df54-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6df54-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6df54-114">**.NET Framework versões:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6df54-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6df54-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="6df54-115">See also</span></span>

- [<span data-ttu-id="6df54-116">Criando perfil de enumerações</span><span class="sxs-lookup"><span data-stu-id="6df54-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
