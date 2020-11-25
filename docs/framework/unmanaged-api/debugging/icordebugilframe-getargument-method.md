---
title: Método ICorDebugILFrame::GetArgument
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: d17179dbeb9564b16c0c95a43502a53a67d3b9b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703155"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="9ca1d-102">Método ICorDebugILFrame::GetArgument</span><span class="sxs-lookup"><span data-stu-id="9ca1d-102">ICorDebugILFrame::GetArgument Method</span></span>

<span data-ttu-id="9ca1d-103">Obtém o valor do argumento especificado neste quadro de ativação da MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="9ca1d-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca1d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ca1d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ca1d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9ca1d-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="9ca1d-106">no O índice do argumento neste quadro de pilha MSIL.</span><span class="sxs-lookup"><span data-stu-id="9ca1d-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9ca1d-107">[out] Um ponteiro para o endereço de um objeto ICorDebugValue que representa o valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="9ca1d-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ca1d-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="9ca1d-108">Remarks</span></span>  

 <span data-ttu-id="9ca1d-109">O `GetArgument` método pode ser usado em um quadro de pilha MSIL ou em um quadro compilado JIT (just-in-time).</span><span class="sxs-lookup"><span data-stu-id="9ca1d-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ca1d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ca1d-110">Requirements</span></span>  

 <span data-ttu-id="9ca1d-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ca1d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ca1d-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ca1d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ca1d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ca1d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ca1d-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ca1d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
