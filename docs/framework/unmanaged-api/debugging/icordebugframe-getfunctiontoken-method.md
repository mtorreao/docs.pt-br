---
title: Método ICorDebugFrame::GetFunctionToken
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
ms.openlocfilehash: 3430c5062bd5633e1178226974b7358783192e51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675978"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="f0902-102">Método ICorDebugFrame::GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="f0902-102">ICorDebugFrame::GetFunctionToken Method</span></span>

<span data-ttu-id="f0902-103">Obtém o token de metadados para a função que contém o código associado a esse quadro de pilha.</span><span class="sxs-lookup"><span data-stu-id="f0902-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0902-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f0902-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0902-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f0902-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="f0902-106">fora Um ponteiro para um `mdMethodDef` token que faz referência aos metadados para a função.</span><span class="sxs-lookup"><span data-stu-id="f0902-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0902-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0902-107">Requirements</span></span>  

 <span data-ttu-id="f0902-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0902-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0902-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0902-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0902-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0902-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0902-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0902-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
