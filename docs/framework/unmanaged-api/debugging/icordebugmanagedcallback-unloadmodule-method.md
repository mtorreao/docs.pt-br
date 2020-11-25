---
title: Método ICorDebugManagedCallback::UnloadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: f24d49189ee81a80397b94ee4113c9514c083dbc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723981"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="cb30a-102">Método ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="cb30a-102">ICorDebugManagedCallback::UnloadModule Method</span></span>

<span data-ttu-id="cb30a-103">Notifica o depurador de que um módulo de Common Language Runtime (DLL) foi descarregado.</span><span class="sxs-lookup"><span data-stu-id="cb30a-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb30a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cb30a-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb30a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cb30a-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="cb30a-106">no Um ponteiro para um objeto ICorDebugAppDomain que representa o domínio do aplicativo que continha o módulo.</span><span class="sxs-lookup"><span data-stu-id="cb30a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="cb30a-107">no Um ponteiro para um objeto ICorDebugModule que representa o módulo.</span><span class="sxs-lookup"><span data-stu-id="cb30a-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb30a-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="cb30a-108">Remarks</span></span>  

 <span data-ttu-id="cb30a-109">O módulo não deve ser usado após esta chamada.</span><span class="sxs-lookup"><span data-stu-id="cb30a-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb30a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb30a-110">Requirements</span></span>  

 <span data-ttu-id="cb30a-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb30a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb30a-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb30a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb30a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb30a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb30a-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb30a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb30a-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="cb30a-115">See also</span></span>

- [<span data-ttu-id="cb30a-116">Método LoadModule</span><span class="sxs-lookup"><span data-stu-id="cb30a-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="cb30a-117">Interface ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="cb30a-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
