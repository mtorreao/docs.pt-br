---
title: Interface ICorDebugGCReferenceEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 12ce800cb83ef4f79710aa441b50be860526023c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728115"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="68174-102">Interface ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="68174-102">ICorDebugGCReferenceEnum Interface</span></span>

<span data-ttu-id="68174-103">Fornece um enumerador para objetos que serão coletados do lixo.</span><span class="sxs-lookup"><span data-stu-id="68174-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68174-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="68174-104">Methods</span></span>  
  
|<span data-ttu-id="68174-105">Método</span><span class="sxs-lookup"><span data-stu-id="68174-105">Method</span></span>|<span data-ttu-id="68174-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="68174-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68174-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="68174-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="68174-108">Obtém o número especificado de instâncias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contêm informações sobre objetos que serão coletados como lixo.</span><span class="sxs-lookup"><span data-stu-id="68174-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68174-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="68174-109">Remarks</span></span>  

 <span data-ttu-id="68174-110">A `ICorDebugGCReferenceEnum` interface implementa a interface "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="68174-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="68174-111">Uma `ICorDebugGCReferenceEnum` instância é populada com instâncias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) chamando o método [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="68174-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="68174-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objetos podem ser enumerados chamando o método [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="68174-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="68174-113">Os objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) na coleção preenchida por esse método representam três tipos de objetos:</span><span class="sxs-lookup"><span data-stu-id="68174-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="68174-114">Objetos de todas as pilhas gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="68174-114">Objects from all managed stacks.</span></span> <span data-ttu-id="68174-115">Isso inclui referências dinâmicas em código gerenciado, bem como objetos criados pelo Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="68174-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="68174-116">Objetos da tabela de identificadores.</span><span class="sxs-lookup"><span data-stu-id="68174-116">Objects from the handle table.</span></span> <span data-ttu-id="68174-117">Isso inclui referências fortes ( `HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT` ) e variáveis estáticas em um módulo.</span><span class="sxs-lookup"><span data-stu-id="68174-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="68174-118">Objetos da fila do finalizador.</span><span class="sxs-lookup"><span data-stu-id="68174-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="68174-119">O finalizador enfileira objetos de raízes até que o finalizador tenha sido executado.</span><span class="sxs-lookup"><span data-stu-id="68174-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68174-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68174-120">Requirements</span></span>  

 <span data-ttu-id="68174-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68174-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68174-122">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68174-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68174-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68174-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68174-124">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68174-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68174-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="68174-125">See also</span></span>

- [<span data-ttu-id="68174-126">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="68174-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
