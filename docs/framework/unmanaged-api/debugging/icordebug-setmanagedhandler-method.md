---
title: Método ICorDebug::SetManagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 97a4a464d3dfb7b333f44ac4206bd880fd171e16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723409"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="5b698-102">Método ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="5b698-102">ICorDebug::SetManagedHandler Method</span></span>

<span data-ttu-id="5b698-103">Especifica o objeto manipulador de eventos para eventos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="5b698-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b698-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5b698-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b698-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="5b698-105">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="5b698-106">no Um ponteiro para um objeto [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) , que é o objeto manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5b698-106">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b698-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="5b698-107">Remarks</span></span>  

 <span data-ttu-id="5b698-108">`SetManagedHandler` deve ser chamado no momento da criação.</span><span class="sxs-lookup"><span data-stu-id="5b698-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="5b698-109">Se a `ICorDebugManagedCallback` implementação não contiver interfaces suficientes para lidar com eventos de depuração para o aplicativo que está sendo depurado, `SetManagedHandler` o retornará um HRESULT de E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="5b698-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b698-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b698-110">Requirements</span></span>  

 <span data-ttu-id="5b698-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b698-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b698-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b698-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b698-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b698-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b698-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b698-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b698-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="5b698-115">See also</span></span>

- [<span data-ttu-id="5b698-116">Interface ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5b698-116">ICorDebug Interface</span></span>](icordebug-interface.md)
