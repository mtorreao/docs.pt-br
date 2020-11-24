---
title: Método ICorDebugEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
ms.openlocfilehash: 28e0cded33b49e3aadc0564bae3a60bee76c4396
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677369"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="1baff-102">Método ICorDebugEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="1baff-102">ICorDebugEnum::Clone Method</span></span>

<span data-ttu-id="1baff-103">Cria uma cópia deste objeto ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="1baff-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1baff-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1baff-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1baff-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1baff-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="1baff-106">fora Um ponteiro para o endereço de um `ICorDebugEnum` objeto que é uma cópia desse `ICorDebugEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="1baff-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1baff-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1baff-107">Requirements</span></span>  

 <span data-ttu-id="1baff-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1baff-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1baff-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1baff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1baff-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1baff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1baff-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1baff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
