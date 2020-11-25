---
title: Método ICorDebugFunctionBreakpoint::GetOffset
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
ms.openlocfilehash: 8b9e483e24068656ddda0a3ecfee5934a2df962d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695888"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="4d2ef-102">Método ICorDebugFunctionBreakpoint::GetOffset</span><span class="sxs-lookup"><span data-stu-id="4d2ef-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>

<span data-ttu-id="4d2ef-103">Obtém o deslocamento do ponto de interrupção dentro da função.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2ef-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4d2ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d2ef-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4d2ef-105">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="4d2ef-106">fora Um ponteiro para o deslocamento do ponto de interrupção.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d2ef-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d2ef-107">Requirements</span></span>  

 <span data-ttu-id="4d2ef-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d2ef-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d2ef-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d2ef-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d2ef-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d2ef-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d2ef-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d2ef-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
