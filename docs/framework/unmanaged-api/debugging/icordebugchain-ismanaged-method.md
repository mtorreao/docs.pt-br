---
title: Método ICorDebugChain::IsManaged
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
ms.openlocfilehash: cfe884c3d26e7a52618eb9945f0af9a167132f05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724371"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="7ce59-102">Método ICorDebugChain::IsManaged</span><span class="sxs-lookup"><span data-stu-id="7ce59-102">ICorDebugChain::IsManaged Method</span></span>

<span data-ttu-id="7ce59-103">Obtém um valor que indica se esta cadeia está executando código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="7ce59-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce59-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7ce59-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ce59-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7ce59-105">Parameters</span></span>  

 `pManaged`  
 <span data-ttu-id="7ce59-106">[fora] `true` Se essa cadeia estiver executando código gerenciado; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="7ce59-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ce59-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ce59-107">Requirements</span></span>  

 <span data-ttu-id="7ce59-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ce59-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ce59-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ce59-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ce59-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ce59-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ce59-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ce59-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
