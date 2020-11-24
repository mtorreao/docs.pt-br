---
title: Método ICorDebugThread::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: dcaa5adc41a9e451b123b088dd900f01d9161689
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688270"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="9a968-102">Método ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="9a968-102">ICorDebugThread::CreateStepper Method</span></span>

<span data-ttu-id="9a968-103">Cria um objeto ICorDebugStepper que permite percorrer o quadro ativo desse ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="9a968-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a968-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9a968-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a968-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9a968-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="9a968-106">fora Um ponteiro para o endereço de um `ICorDebugStepper` objeto que permite percorrer o quadro ativo desse thread.</span><span class="sxs-lookup"><span data-stu-id="9a968-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a968-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="9a968-107">Remarks</span></span>  

 <span data-ttu-id="9a968-108">O quadro ativo pode ser um código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="9a968-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="9a968-109">A `ICorDebugStepper` interface deve ser usada para executar a depuração real.</span><span class="sxs-lookup"><span data-stu-id="9a968-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a968-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a968-110">Requirements</span></span>  

 <span data-ttu-id="9a968-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a968-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a968-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a968-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a968-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a968-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a968-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a968-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
