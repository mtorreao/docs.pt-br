---
title: Método ICorDebugThread2::GetTaskID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: 9b17a179745af65bde05527bd0157f3ce06c12c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678643"
---
# <a name="icordebugthread2gettaskid-method"></a><span data-ttu-id="1a9ec-102">Método ICorDebugThread2::GetTaskID</span><span class="sxs-lookup"><span data-stu-id="1a9ec-102">ICorDebugThread2::GetTaskID Method</span></span>

<span data-ttu-id="1a9ec-103">Obtém o identificador da tarefa em execução neste thread.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-103">Gets the identifier of the task running on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a9ec-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1a9ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a9ec-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1a9ec-105">Parameters</span></span>  

 `pTaskId`  
 <span data-ttu-id="1a9ec-106">fora Um ponteiro para o identificador da tarefa em execução no thread representado por esse objeto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-106">[out] A pointer to the identifier of the task running on the thread represented by this ICorDebugThread2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a9ec-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="1a9ec-107">Remarks</span></span>  

 <span data-ttu-id="1a9ec-108">Uma tarefa só poderá ser executada no thread se o thread estiver associado a uma conexão.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-108">A task can only be running on the thread if the thread is associated with a connection.</span></span> <span data-ttu-id="1a9ec-109">`GetTaskID` retornará zero `pTaskId` se o thread não estiver associado a uma conexão.</span><span class="sxs-lookup"><span data-stu-id="1a9ec-109">`GetTaskID` returns zero in `pTaskId` if the thread is not associated with a connection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a9ec-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a9ec-110">Requirements</span></span>  

 <span data-ttu-id="1a9ec-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a9ec-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a9ec-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a9ec-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a9ec-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a9ec-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a9ec-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a9ec-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
