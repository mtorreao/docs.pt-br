---
title: Método ICorDebugProcess::ModifyLogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: 3ac1b3606131f534195df9b6b59bf72b1bff27fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724527"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="417b3-102">Método ICorDebugProcess::ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="417b3-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>

<span data-ttu-id="417b3-103">Define o nível de severidade da opção de log especificada.</span><span class="sxs-lookup"><span data-stu-id="417b3-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417b3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="417b3-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="417b3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="417b3-105">Parameters</span></span>  

 `pLogSwitchName`  
 <span data-ttu-id="417b3-106">no Um ponteiro para uma cadeia de caracteres que especifica o nome do comutador de log.</span><span class="sxs-lookup"><span data-stu-id="417b3-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="417b3-107">no O nível de severidade a ser definido para o comutador de log especificado.</span><span class="sxs-lookup"><span data-stu-id="417b3-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="417b3-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="417b3-108">Remarks</span></span>  

 <span data-ttu-id="417b3-109">Este método é válido somente depois que o retorno de chamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) ocorreu.</span><span class="sxs-lookup"><span data-stu-id="417b3-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="417b3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="417b3-110">Requirements</span></span>  

 <span data-ttu-id="417b3-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="417b3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="417b3-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="417b3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="417b3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="417b3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="417b3-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="417b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
