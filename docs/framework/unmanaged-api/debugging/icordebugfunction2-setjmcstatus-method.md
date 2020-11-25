---
title: Método ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
ms.openlocfilehash: 55f219b5b834f365b87440e69bfa7d2c4e519235
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696083"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="9f299-102">Método ICorDebugFunction2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="9f299-102">ICorDebugFunction2::SetJMCStatus Method</span></span>

<span data-ttu-id="9f299-103">Marca a função representada por este ICorDebugFunction2 para Apenas Meu Código stepping.</span><span class="sxs-lookup"><span data-stu-id="9f299-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f299-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f299-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f299-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9f299-105">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="9f299-106">no Defina como `true` para marcar a função como código do usuário; caso contrário, defina como `false` .</span><span class="sxs-lookup"><span data-stu-id="9f299-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="9f299-107">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9f299-107">Return Values</span></span>  
  
|<span data-ttu-id="9f299-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f299-108">HRESULT</span></span>|<span data-ttu-id="9f299-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9f299-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9f299-110">A função foi marcada com êxito.</span><span class="sxs-lookup"><span data-stu-id="9f299-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="9f299-111">A função não pôde ser marcada como código de usuário porque não pode ser depurada.</span><span class="sxs-lookup"><span data-stu-id="9f299-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f299-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="9f299-112">Remarks</span></span>  

 <span data-ttu-id="9f299-113">Um Apenas Meu Código stepper ignorará o código que não é do usuário.</span><span class="sxs-lookup"><span data-stu-id="9f299-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="9f299-114">O código do usuário deve ser um subconjunto de código depurável.</span><span class="sxs-lookup"><span data-stu-id="9f299-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f299-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f299-115">Requirements</span></span>  

 <span data-ttu-id="9f299-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f299-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f299-117">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f299-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f299-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f299-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f299-119">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f299-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
