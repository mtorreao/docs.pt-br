---
title: Enumeração CorDebugGCType
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
ms.openlocfilehash: 6b3075613af0403527ecf67d574c0f5733a5cd8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712606"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="54947-102">Enumeração CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="54947-102">CorDebugGCType Enumeration</span></span>

<span data-ttu-id="54947-103">Indica se o coletor de lixo está sendo executado em uma estação de trabalho ou em um servidor.</span><span class="sxs-lookup"><span data-stu-id="54947-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54947-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="54947-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="54947-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="54947-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="54947-106">Membros</span><span class="sxs-lookup"><span data-stu-id="54947-106">Members</span></span>  
  
|<span data-ttu-id="54947-107">Nome do membro</span><span class="sxs-lookup"><span data-stu-id="54947-107">Member name</span></span>|<span data-ttu-id="54947-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="54947-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="54947-109">O coletor de lixo está em execução em uma estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54947-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="54947-110">O coletor de lixo está em execução em um servidor.</span><span class="sxs-lookup"><span data-stu-id="54947-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54947-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="54947-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54947-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54947-112">Requirements</span></span>  

 <span data-ttu-id="54947-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54947-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54947-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54947-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54947-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54947-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54947-116">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54947-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54947-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="54947-117">See also</span></span>

- [<span data-ttu-id="54947-118">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="54947-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
