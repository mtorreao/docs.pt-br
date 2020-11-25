---
title: Enumeração CorDebugCreateProcessFlags
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
ms.openlocfilehash: f6f589656a3063fc89bd276b32d0ed751fd8d2d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733393"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="3c175-102">Enumeração CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="3c175-102">CorDebugCreateProcessFlags Enumeration</span></span>

<span data-ttu-id="3c175-103">Fornece opções de depuração adicionais que podem ser usadas em uma chamada para o método [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3c175-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c175-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3c175-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3c175-105">Membros</span><span class="sxs-lookup"><span data-stu-id="3c175-105">Members</span></span>  
  
|<span data-ttu-id="3c175-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3c175-106">Member</span></span>|<span data-ttu-id="3c175-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="3c175-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="3c175-108">Não há opções especiais definidas.</span><span class="sxs-lookup"><span data-stu-id="3c175-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c175-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c175-109">Requirements</span></span>  

 <span data-ttu-id="3c175-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c175-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c175-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c175-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c175-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c175-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c175-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c175-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c175-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="3c175-114">See also</span></span>

- [<span data-ttu-id="3c175-115">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="3c175-115">Debugging Enumerations</span></span>](debugging-enumerations.md)
