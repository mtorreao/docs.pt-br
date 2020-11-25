---
title: Método ICorDebug::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: cf9c9d11c4725908fcf7ff4a0c91882b70a80190
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723370"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="40a91-102">Método ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="40a91-102">ICorDebug::Terminate Method</span></span>

<span data-ttu-id="40a91-103">Encerra o `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="40a91-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40a91-104">`Terminate` Não deve ser chamado até que um retorno de chamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) tenha sido recebido para todos os processos sendo depurados.</span><span class="sxs-lookup"><span data-stu-id="40a91-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a91-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="40a91-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="40a91-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="40a91-106">Remarks</span></span>  

 <span data-ttu-id="40a91-107">`Terminate` deve ser chamado quando o `ICorDebug` objeto não for mais necessário.</span><span class="sxs-lookup"><span data-stu-id="40a91-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40a91-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40a91-108">Requirements</span></span>  

 <span data-ttu-id="40a91-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40a91-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40a91-110">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40a91-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40a91-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40a91-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40a91-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40a91-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a91-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="40a91-113">See also</span></span>

- [<span data-ttu-id="40a91-114">Interface ICorDebug</span><span class="sxs-lookup"><span data-stu-id="40a91-114">ICorDebug Interface</span></span>](icordebug-interface.md)
