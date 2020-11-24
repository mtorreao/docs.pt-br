---
title: Método ICorDebugFrame::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
ms.openlocfilehash: 29dc87bf465fc9751b5af795f7640b095e535e63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690376"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="42485-102">Método ICorDebugFrame::GetCode</span><span class="sxs-lookup"><span data-stu-id="42485-102">ICorDebugFrame::GetCode Method</span></span>

<span data-ttu-id="42485-103">Obtém um ponteiro para o código associado a este quadro de pilhas.</span><span class="sxs-lookup"><span data-stu-id="42485-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42485-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="42485-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42485-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="42485-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="42485-106">fora Um ponteiro para o endereço de um objeto ICorDebugCode que representa o código associado a esse quadro.</span><span class="sxs-lookup"><span data-stu-id="42485-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42485-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42485-107">Requirements</span></span>  

 <span data-ttu-id="42485-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42485-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42485-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42485-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42485-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42485-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42485-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42485-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
