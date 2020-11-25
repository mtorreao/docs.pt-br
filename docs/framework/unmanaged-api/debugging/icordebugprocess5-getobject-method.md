---
title: Método ICorDebugProcess5::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
ms.openlocfilehash: ff2913399e1dbeb33bbfb697058db3caf2a8d1fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713100"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="813ae-102">Método ICorDebugProcess5::GetObject</span><span class="sxs-lookup"><span data-stu-id="813ae-102">ICorDebugProcess5::GetObject Method</span></span>

<span data-ttu-id="813ae-103">Converte um endereço de objeto em um objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="813ae-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="813ae-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="813ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="813ae-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="813ae-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="813ae-106">no O endereço do objeto.</span><span class="sxs-lookup"><span data-stu-id="813ae-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="813ae-107">fora Um ponteiro para o endereço de um objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="813ae-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="813ae-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="813ae-108">Remarks</span></span>  

 <span data-ttu-id="813ae-109">Se `addr` o não apontar para um objeto gerenciado válido, o `GetObject` método retornará `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="813ae-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="813ae-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="813ae-110">Requirements</span></span>  

 <span data-ttu-id="813ae-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="813ae-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="813ae-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="813ae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="813ae-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="813ae-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="813ae-114">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="813ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="813ae-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="813ae-115">See also</span></span>

- [<span data-ttu-id="813ae-116">Interface ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="813ae-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="813ae-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="813ae-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
