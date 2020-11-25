---
title: Método ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: c9c0598f8e7b3e8654124f50663c912f3cd61659
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709292"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="eadb8-102">Método ICorDebugNativeFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="eadb8-102">ICorDebugNativeFrame::GetIP Method</span></span>

<span data-ttu-id="eadb8-103">Obtém o local de deslocamento de código nativo para o qual o ponteiro de instrução está definido no momento.</span><span class="sxs-lookup"><span data-stu-id="eadb8-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eadb8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eadb8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eadb8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="eadb8-105">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="eadb8-106">fora Um ponteiro para o local de deslocamento no código nativo.</span><span class="sxs-lookup"><span data-stu-id="eadb8-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eadb8-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="eadb8-107">Remarks</span></span>  

 <span data-ttu-id="eadb8-108">Se o registro de ativação representado por esse "ICorDebugNativeFrame" estiver ativo, o deslocamento será o endereço da próxima instrução a ser executada.</span><span class="sxs-lookup"><span data-stu-id="eadb8-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="eadb8-109">Se esse quadro de pilhas não estiver ativo, o deslocamento será o endereço da próxima instrução a ser executada quando o registro de ativação for reativado.</span><span class="sxs-lookup"><span data-stu-id="eadb8-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eadb8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eadb8-110">Requirements</span></span>  

 <span data-ttu-id="eadb8-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eadb8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eadb8-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eadb8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eadb8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eadb8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eadb8-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eadb8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eadb8-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="eadb8-115">See also</span></span>
