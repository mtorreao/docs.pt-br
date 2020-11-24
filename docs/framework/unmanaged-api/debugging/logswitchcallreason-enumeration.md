---
title: Enumeração LogSwitchCallReason
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
ms.openlocfilehash: dfb34595530a47b74762610f5824b68ea00a8a69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671935"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="1d689-102">Enumeração LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="1d689-102">LogSwitchCallReason Enumeration</span></span>

<span data-ttu-id="1d689-103">Indica a operação que foi realizada em uma alternação entre depuração/rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1d689-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d689-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1d689-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="1d689-105">Membros</span><span class="sxs-lookup"><span data-stu-id="1d689-105">Members</span></span>  
  
|<span data-ttu-id="1d689-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1d689-106">Member</span></span>|<span data-ttu-id="1d689-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1d689-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="1d689-108">Uma opção de depuração/rastreamento foi criada.</span><span class="sxs-lookup"><span data-stu-id="1d689-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="1d689-109">Uma opção de depuração/rastreamento foi modificada.</span><span class="sxs-lookup"><span data-stu-id="1d689-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="1d689-110">Uma opção de depuração/rastreamento foi excluída.</span><span class="sxs-lookup"><span data-stu-id="1d689-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d689-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d689-111">Requirements</span></span>  

 <span data-ttu-id="1d689-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d689-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d689-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d689-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d689-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d689-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d689-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d689-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d689-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="1d689-116">See also</span></span>

- [<span data-ttu-id="1d689-117">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="1d689-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
