---
title: Método ICorDebugBreakpoint::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
ms.openlocfilehash: 064f9727b221dd64a58f8cd5e103271e37020786
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730169"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="3e2f8-102">Método ICorDebugBreakpoint::IsActive</span><span class="sxs-lookup"><span data-stu-id="3e2f8-102">ICorDebugBreakpoint::IsActive Method</span></span>

<span data-ttu-id="3e2f8-103">Obtém um valor que indica se ele `ICorDebugBreakpoint` está ativo.</span><span class="sxs-lookup"><span data-stu-id="3e2f8-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e2f8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3e2f8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e2f8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3e2f8-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="3e2f8-106">[fora] `true` Se esse ponto de interrupção estiver ativo; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="3e2f8-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e2f8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e2f8-107">Requirements</span></span>  

 <span data-ttu-id="3e2f8-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e2f8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e2f8-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e2f8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e2f8-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e2f8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e2f8-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e2f8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
