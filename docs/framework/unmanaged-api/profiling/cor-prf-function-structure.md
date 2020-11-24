---
title: Estrutura COR_PRF_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
ms.openlocfilehash: 1da8f414ccf0c1eed3ec7dde842dd381440a3fa9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674951"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="15b98-102">Estrutura COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="15b98-102">COR_PRF_FUNCTION Structure</span></span>

<span data-ttu-id="15b98-103">Fornece uma representação única de uma função pela combinação de sua ID com a ID de sua versão recompilada.</span><span class="sxs-lookup"><span data-stu-id="15b98-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b98-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="15b98-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="15b98-105">Membros</span><span class="sxs-lookup"><span data-stu-id="15b98-105">Members</span></span>  
  
|<span data-ttu-id="15b98-106">Membro</span><span class="sxs-lookup"><span data-stu-id="15b98-106">Member</span></span>|<span data-ttu-id="15b98-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="15b98-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="15b98-108">A ID da função.</span><span class="sxs-lookup"><span data-stu-id="15b98-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="15b98-109">A ID da função recompilada.</span><span class="sxs-lookup"><span data-stu-id="15b98-109">The ID of the recompiled function.</span></span> <span data-ttu-id="15b98-110">Um valor de 0 (zero) representa a versão original da função.</span><span class="sxs-lookup"><span data-stu-id="15b98-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15b98-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="15b98-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15b98-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15b98-112">Requirements</span></span>  

 <span data-ttu-id="15b98-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15b98-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b98-114">**Cabeçalho:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="15b98-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="15b98-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15b98-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15b98-116">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15b98-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b98-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="15b98-117">See also</span></span>

- [<span data-ttu-id="15b98-118">Estruturas de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="15b98-118">Profiling Structures</span></span>](profiling-structures.md)
