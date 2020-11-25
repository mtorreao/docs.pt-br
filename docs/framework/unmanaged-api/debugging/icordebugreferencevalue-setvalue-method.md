---
title: Método ICorDebugReferenceValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
ms.openlocfilehash: 3fdd3180a01e4609ac40fd358879c0d2569234ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728375"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="9939f-102">Método ICorDebugReferenceValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="9939f-102">ICorDebugReferenceValue::SetValue Method</span></span>

<span data-ttu-id="9939f-103">Define o endereço de memória especificado.</span><span class="sxs-lookup"><span data-stu-id="9939f-103">Sets the specified memory address.</span></span> <span data-ttu-id="9939f-104">Ou seja, esse método define esse ICorDebugReferenceValue para apontar para um objeto.</span><span class="sxs-lookup"><span data-stu-id="9939f-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9939f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9939f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9939f-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9939f-106">Parameters</span></span>  

 `value`  
 <span data-ttu-id="9939f-107">no Um `CORDB_ADDRESS` valor que especifica o endereço do objeto para o qual este `ICorDebugReferenceValue` aponta.</span><span class="sxs-lookup"><span data-stu-id="9939f-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9939f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9939f-108">Requirements</span></span>  

 <span data-ttu-id="9939f-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9939f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9939f-110">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9939f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9939f-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9939f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9939f-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9939f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
