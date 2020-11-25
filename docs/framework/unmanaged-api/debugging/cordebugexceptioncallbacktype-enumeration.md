---
title: Enumeração CorDebugExceptionCallbackType
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
ms.openlocfilehash: cddcf66939a2ae7ab9e7f63a6fd61b72c56f6c7a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712723"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="8c5e5-102">Enumeração CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="8c5e5-102">CorDebugExceptionCallbackType Enumeration</span></span>

<span data-ttu-id="8c5e5-103">Indica o tipo de retorno de chamada que é feito de um evento [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c5e5-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5e5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8c5e5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="8c5e5-105">Membros</span><span class="sxs-lookup"><span data-stu-id="8c5e5-105">Members</span></span>  
  
|<span data-ttu-id="8c5e5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8c5e5-106">Member</span></span>|<span data-ttu-id="8c5e5-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8c5e5-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="8c5e5-108">Uma exceção foi lançada.</span><span class="sxs-lookup"><span data-stu-id="8c5e5-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="8c5e5-109">O processo de windup de exceção inseriu o código do usuário.</span><span class="sxs-lookup"><span data-stu-id="8c5e5-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="8c5e5-110">O processo windup de exceção encontrou um `catch` bloco no código do usuário.</span><span class="sxs-lookup"><span data-stu-id="8c5e5-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="8c5e5-111">A exceção não foi tratada.</span><span class="sxs-lookup"><span data-stu-id="8c5e5-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c5e5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c5e5-112">Requirements</span></span>  

 <span data-ttu-id="8c5e5-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c5e5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c5e5-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c5e5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c5e5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c5e5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c5e5-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c5e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5e5-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c5e5-117">See also</span></span>

- [<span data-ttu-id="8c5e5-118">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="8c5e5-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
