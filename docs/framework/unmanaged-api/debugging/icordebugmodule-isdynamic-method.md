---
title: Método ICorDebugModule::IsDynamic
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
ms.openlocfilehash: 98c01993a85ed07d961902d8a098a96df4702c76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709824"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="1d624-102">Método ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="1d624-102">ICorDebugModule::IsDynamic Method</span></span>

<span data-ttu-id="1d624-103">Obtém um valor que indica se este módulo é dinâmico.</span><span class="sxs-lookup"><span data-stu-id="1d624-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d624-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1d624-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d624-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1d624-105">Parameters</span></span>  

 `pDynamic`  
 <span data-ttu-id="1d624-106">[fora] `true` Se esse módulo for dinâmico; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="1d624-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d624-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="1d624-107">Remarks</span></span>  

 <span data-ttu-id="1d624-108">Um módulo dinâmico pode adicionar novas classes e excluir classes existentes mesmo depois que o módulo tiver sido carregado.</span><span class="sxs-lookup"><span data-stu-id="1d624-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="1d624-109">Os retornos de chamada [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) informam ao depurador quando uma classe foi adicionada ou excluída.</span><span class="sxs-lookup"><span data-stu-id="1d624-109">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d624-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d624-110">Requirements</span></span>  

 <span data-ttu-id="1d624-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d624-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d624-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d624-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d624-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d624-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d624-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d624-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
