---
title: Método ICorDebugILFrame::GetLocalVariable
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
ms.openlocfilehash: 54ecce830b928ded115233eb99932cc15a471033
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703129"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="60615-102">Método ICorDebugILFrame::GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="60615-102">ICorDebugILFrame::GetLocalVariable Method</span></span>

<span data-ttu-id="60615-103">Obtém o valor da variável local especificada neste quadro de ativação da MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="60615-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60615-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="60615-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60615-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="60615-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="60615-106">no O índice da variável local neste quadro da pilha MSIL.</span><span class="sxs-lookup"><span data-stu-id="60615-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="60615-107">[out] Um ponteiro para o endereço de um objeto ICorDebugValue que representa o valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="60615-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60615-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="60615-108">Remarks</span></span>  

 <span data-ttu-id="60615-109">O `GetLocalVariable` método pode ser usado em um quadro de pilha MSIL ou em um quadro compilado JIT (just-in-time).</span><span class="sxs-lookup"><span data-stu-id="60615-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60615-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60615-110">Requirements</span></span>  

 <span data-ttu-id="60615-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60615-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60615-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60615-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60615-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60615-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60615-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60615-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
