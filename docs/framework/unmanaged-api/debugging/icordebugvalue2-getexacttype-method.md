---
title: Método ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720354"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="dd357-102">Método ICorDebugValue2::GetExactType</span><span class="sxs-lookup"><span data-stu-id="dd357-102">ICorDebugValue2::GetExactType Method</span></span>

<span data-ttu-id="dd357-103">Obtém um ponteiro de interface para um objeto "ICorDebugType" que representa o <xref:System.Type> desse valor.</span><span class="sxs-lookup"><span data-stu-id="dd357-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd357-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd357-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd357-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dd357-105">Parameters</span></span>  

 `ppType`  
 <span data-ttu-id="dd357-106">fora Um ponteiro para o endereço de um `ICorDebugType` objeto que representa o <xref:System.Type> do valor representado por esse objeto "ICorDebugValue2".</span><span class="sxs-lookup"><span data-stu-id="dd357-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd357-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="dd357-107">Remarks</span></span>  

 <span data-ttu-id="dd357-108">O método com reconhecimento de genéricos `GetExactType` substitui os métodos [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) e [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , sendo que cada um retorna informações sobre o tipo de um valor.</span><span class="sxs-lookup"><span data-stu-id="dd357-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd357-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd357-109">Requirements</span></span>  

 <span data-ttu-id="dd357-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd357-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd357-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd357-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd357-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd357-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd357-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd357-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd357-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="dd357-114">See also</span></span>
