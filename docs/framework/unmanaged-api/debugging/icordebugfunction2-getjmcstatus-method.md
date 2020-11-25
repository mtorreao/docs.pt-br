---
title: Método ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 747f165a98dfd1264ea58d61aaa1615c6d71e073
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726282"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="34b4f-102">Método ICorDebugFunction2::GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="34b4f-102">ICorDebugFunction2::GetJMCStatus Method</span></span>

<span data-ttu-id="34b4f-103">Obtém um valor que indica se a função representada por esse objeto ICorDebugFunction2 está marcada como código de usuário.</span><span class="sxs-lookup"><span data-stu-id="34b4f-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34b4f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="34b4f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34b4f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="34b4f-105">Parameters</span></span>  

 `pbIsJustMyCode`  
 <span data-ttu-id="34b4f-106">fora Um ponteiro para um valor booliano `true` , se essa função estiver marcada como código de usuário; caso contrário, o valor será `false` .</span><span class="sxs-lookup"><span data-stu-id="34b4f-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34b4f-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="34b4f-107">Remarks</span></span>  

 <span data-ttu-id="34b4f-108">Se a função representada por isso `ICorDebugFunction2` não puder ser depurada, `pbIsJustMyCode` sempre será `false` .</span><span class="sxs-lookup"><span data-stu-id="34b4f-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34b4f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34b4f-109">Requirements</span></span>  

 <span data-ttu-id="34b4f-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34b4f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34b4f-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34b4f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34b4f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34b4f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34b4f-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34b4f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
