---
title: Método ICorDebugReferenceValue::Dereference
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: cbcee923ecbb1106bb129f05d2e602a0fd17258d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732475"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="7d97b-102">Método ICorDebugReferenceValue::Dereference</span><span class="sxs-lookup"><span data-stu-id="7d97b-102">ICorDebugReferenceValue::Dereference Method</span></span>

<span data-ttu-id="7d97b-103">Obtém o objeto que é referenciado.</span><span class="sxs-lookup"><span data-stu-id="7d97b-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d97b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7d97b-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d97b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7d97b-105">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="7d97b-106">fora Um ponteiro para o endereço de um ICorDebugValue que representa o objeto ao qual esse objeto ICorDebugReferenceValue aponta.</span><span class="sxs-lookup"><span data-stu-id="7d97b-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d97b-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="7d97b-107">Remarks</span></span>  

 <span data-ttu-id="7d97b-108">O `ICorDebugValue` objeto é válido somente enquanto sua referência ainda não foi desabilitada.</span><span class="sxs-lookup"><span data-stu-id="7d97b-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d97b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d97b-109">Requirements</span></span>  

 <span data-ttu-id="7d97b-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d97b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d97b-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d97b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d97b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d97b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d97b-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d97b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
