---
title: Enumeração CLRDataEnumMemoryFlags
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
ms.openlocfilehash: 9a82162023fa05e85fc9bbeb16961f2aafd9a4ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729792"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="20007-102">Enumeração CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="20007-102">CLRDataEnumMemoryFlags Enumeration</span></span>

<span data-ttu-id="20007-103">Indica quais regiões de memória uma chamada para o método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) deve incluir.</span><span class="sxs-lookup"><span data-stu-id="20007-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20007-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="20007-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="20007-105">Membros</span><span class="sxs-lookup"><span data-stu-id="20007-105">Members</span></span>  
  
|<span data-ttu-id="20007-106">Membro</span><span class="sxs-lookup"><span data-stu-id="20007-106">Member</span></span>|<span data-ttu-id="20007-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="20007-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="20007-108">Um minidespejo, ou seja, um despejo de memória esparso.</span><span class="sxs-lookup"><span data-stu-id="20007-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="20007-109">Um despejo de pilha completo.</span><span class="sxs-lookup"><span data-stu-id="20007-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20007-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20007-110">Requirements</span></span>  

 <span data-ttu-id="20007-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20007-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20007-112">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="20007-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="20007-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20007-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20007-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20007-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20007-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="20007-115">See also</span></span>

- [<span data-ttu-id="20007-116">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="20007-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
