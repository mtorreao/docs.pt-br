---
title: Método ICorDebugAppDomain::Attach
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: d133cacb611a1c7bd03d7653f46c2e5fb1acc043
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723344"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="4d3db-102">Método ICorDebugAppDomain::Attach</span><span class="sxs-lookup"><span data-stu-id="4d3db-102">ICorDebugAppDomain::Attach Method</span></span>

<span data-ttu-id="4d3db-103">Anexa o depurador ao domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4d3db-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d3db-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4d3db-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4d3db-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="4d3db-105">Remarks</span></span>  

 <span data-ttu-id="4d3db-106">O depurador deve ser anexado ao domínio do aplicativo para receber eventos e habilitar a depuração do domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4d3db-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d3db-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d3db-107">Requirements</span></span>  

 <span data-ttu-id="4d3db-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d3db-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d3db-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d3db-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d3db-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d3db-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d3db-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d3db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
