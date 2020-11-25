---
title: Método ICorDebugProcess5::EnumerateHandles
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: 607847180cca039d4c71f26e446a17a14dc2fb9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724332"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="9501c-102">Método ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="9501c-102">ICorDebugProcess5::EnumerateHandles Method</span></span>

<span data-ttu-id="9501c-103">Obtém um enumerador para identificadores de objeto em um processo.</span><span class="sxs-lookup"><span data-stu-id="9501c-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9501c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9501c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9501c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9501c-105">Parameters</span></span>  

 `types`  
 <span data-ttu-id="9501c-106">no Uma combinação bits de valores [CorGCReferenceType](corgcreferencetype-enumeration.md) que especifica o tipo de identificadores a serem incluídos na coleção.</span><span class="sxs-lookup"><span data-stu-id="9501c-106">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="9501c-107">fora Um ponteiro para o endereço de um [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) que é um enumerador para os objetos a serem coletados como lixo.</span><span class="sxs-lookup"><span data-stu-id="9501c-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9501c-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="9501c-108">Remarks</span></span>  

 <span data-ttu-id="9501c-109">`EnumerateHandles` é uma função auxiliar que dá suporte à inspeção da tabela de identificadores.</span><span class="sxs-lookup"><span data-stu-id="9501c-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="9501c-110">Ele é semelhante ao método [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) , exceto que, em vez de preencher uma coleção [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) com todos os objetos a serem coletados pelo lixo, ele inclui somente objetos que têm identificadores da tabela de identificadores.</span><span class="sxs-lookup"><span data-stu-id="9501c-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="9501c-111">O `types` parâmetro especifica os tipos de identificador a serem incluídos na coleção.</span><span class="sxs-lookup"><span data-stu-id="9501c-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="9501c-112">`types` pode ser qualquer um dos três membros a seguir da enumeração [CorGCReferenceType](corgcreferencetype-enumeration.md) :</span><span class="sxs-lookup"><span data-stu-id="9501c-112">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="9501c-113">`CorHandleStrongOnly` (lida apenas com referências fortes).</span><span class="sxs-lookup"><span data-stu-id="9501c-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="9501c-114">`CorHandleWeakOnly` (lida apenas com referências fracas).</span><span class="sxs-lookup"><span data-stu-id="9501c-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="9501c-115">`CorHandleAll` (todos os identificadores).</span><span class="sxs-lookup"><span data-stu-id="9501c-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9501c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9501c-116">Requirements</span></span>  

 <span data-ttu-id="9501c-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9501c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9501c-118">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9501c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9501c-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9501c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9501c-120">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9501c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9501c-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="9501c-121">See also</span></span>

- [<span data-ttu-id="9501c-122">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="9501c-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="9501c-123">Depuração</span><span class="sxs-lookup"><span data-stu-id="9501c-123">Debugging</span></span>](index.md)
