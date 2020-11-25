---
title: Método ICorDebugThread::GetActiveChain
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: e6b1d78b2bd95ea27f4b19a045cd2680342e8a80
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728089"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="a1bd0-102">Método ICorDebugThread::GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="a1bd0-102">ICorDebugThread::GetActiveChain Method</span></span>

<span data-ttu-id="a1bd0-103">Obtém um ponteiro de interface para a cadeia de pilha ativa (mais recente) neste objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="a1bd0-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bd0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a1bd0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1bd0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a1bd0-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="a1bd0-106">fora Um ponteiro para o endereço de um objeto ICorDebugChain que representa a cadeia de pilha.</span><span class="sxs-lookup"><span data-stu-id="a1bd0-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1bd0-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="a1bd0-107">Remarks</span></span>  

 <span data-ttu-id="a1bd0-108">O `ppChain` parâmetro será NULL se nenhuma cadeia de pilha estiver ativa no momento.</span><span class="sxs-lookup"><span data-stu-id="a1bd0-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1bd0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1bd0-109">Requirements</span></span>  

 <span data-ttu-id="a1bd0-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1bd0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1bd0-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1bd0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1bd0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1bd0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1bd0-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1bd0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
