---
title: Método ICorDebugInternalFrame::GetFrameType
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
ms.openlocfilehash: c675ba4b56cecd1990184cd2f0e805250c3dfeb7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724878"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="e8689-102">Método ICorDebugInternalFrame::GetFrameType</span><span class="sxs-lookup"><span data-stu-id="e8689-102">ICorDebugInternalFrame::GetFrameType Method</span></span>

<span data-ttu-id="e8689-103">Obtém o tipo deste quadro interno.</span><span class="sxs-lookup"><span data-stu-id="e8689-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8689-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e8689-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8689-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e8689-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="e8689-106">fora Um ponteiro para um valor da enumeração CorDebugInternalFrameType que indica o tipo de quadro interno representado por esse `ICorDebugInternalFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="e8689-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8689-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="e8689-107">Remarks</span></span>  

 <span data-ttu-id="e8689-108">O tipo de quadro interno nunca será STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="e8689-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="e8689-109">Os depuradores devem ignorar normalmente os tipos de quadro internos não reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="e8689-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8689-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8689-110">Requirements</span></span>  

 <span data-ttu-id="e8689-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8689-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8689-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8689-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8689-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8689-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8689-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8689-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
