---
title: Enumeração CorDebugGenerationTypes
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
ms.openlocfilehash: 189a276b4228038ab1d70620ce3a4a0f4342b245
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712515"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="7660f-102">Enumeração CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="7660f-102">CorDebugGenerationTypes Enumeration</span></span>

<span data-ttu-id="7660f-103">Especifica a geração de uma região de memória no heap gerenciado.</span><span class="sxs-lookup"><span data-stu-id="7660f-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7660f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7660f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="7660f-105">Membros</span><span class="sxs-lookup"><span data-stu-id="7660f-105">Members</span></span>  
  
|<span data-ttu-id="7660f-106">Nome do membro</span><span class="sxs-lookup"><span data-stu-id="7660f-106">Member name</span></span>|<span data-ttu-id="7660f-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="7660f-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="7660f-108">Geração 0.</span><span class="sxs-lookup"><span data-stu-id="7660f-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="7660f-109">Geração 1.</span><span class="sxs-lookup"><span data-stu-id="7660f-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="7660f-110">Geração 2.</span><span class="sxs-lookup"><span data-stu-id="7660f-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="7660f-111">A heap de objeto grande.</span><span class="sxs-lookup"><span data-stu-id="7660f-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7660f-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="7660f-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7660f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7660f-113">Requirements</span></span>  

 <span data-ttu-id="7660f-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7660f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7660f-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7660f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7660f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7660f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7660f-117">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7660f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7660f-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="7660f-118">See also</span></span>

- [<span data-ttu-id="7660f-119">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="7660f-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
