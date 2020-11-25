---
title: Interface ICorDebugProcess5
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
ms.openlocfilehash: cef69ac7e3572b67dd676ce8408e4210d93accf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717572"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="f75aa-102">Interface ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="f75aa-102">ICorDebugProcess5 Interface</span></span>

<span data-ttu-id="f75aa-103">Estende a interface ICorDebugProcess para dar suporte ao acesso ao heap gerenciado, para fornecer informações sobre a coleta de lixo de objetos gerenciados e para determinar se um depurador carrega imagens do cache de imagem nativa local do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f75aa-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f75aa-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f75aa-104">Methods</span></span>  
  
|<span data-ttu-id="f75aa-105">Método</span><span class="sxs-lookup"><span data-stu-id="f75aa-105">Method</span></span>|<span data-ttu-id="f75aa-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f75aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f75aa-107">Método EnableNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="f75aa-107">EnableNGenPolicy Method</span></span>](icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="f75aa-108">Define um valor que determina como um aplicativo carrega imagens nativas durante a execução em um depurador gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f75aa-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="f75aa-109">Método EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="f75aa-109">EnumerateGCReferences Method</span></span>](icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="f75aa-110">Obtém um enumerador para todos os objetos que devem ser coletados pelo lixo em um processo.</span><span class="sxs-lookup"><span data-stu-id="f75aa-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="f75aa-111">Método EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="f75aa-111">EnumerateHandles Method</span></span>](icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="f75aa-112">Obtém um enumerador para identificadores de objeto em um processo.</span><span class="sxs-lookup"><span data-stu-id="f75aa-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="f75aa-113">Método EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="f75aa-113">EnumerateHeap Method</span></span>](icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="f75aa-114">Obtém um enumerador para objetos no heap gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f75aa-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="f75aa-115">Método EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="f75aa-115">EnumerateHeapRegions Method</span></span>](icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="f75aa-116">Obtém um enumerador para regiões do heap gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f75aa-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="f75aa-117">Método GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="f75aa-117">GetArrayLayout Method</span></span>](icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="f75aa-118">Obtém informações sobre o layout de uma matriz na memória.</span><span class="sxs-lookup"><span data-stu-id="f75aa-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="f75aa-119">Método GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="f75aa-119">GetGCHeapInformation Method</span></span>](icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="f75aa-120">Obtém um ponteiro para uma estrutura de [COR_HEAPINFO](cor-heapinfo-structure.md) que contém informações sobre objetos que devem ser coletados pelo lixo no heap gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f75aa-120">Gets a pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="f75aa-121">Método GetObject</span><span class="sxs-lookup"><span data-stu-id="f75aa-121">GetObject Method</span></span>](icordebugprocess5-getobject-method.md)|<span data-ttu-id="f75aa-122">Obtém um ponteiro para um objeto no heap gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f75aa-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="f75aa-123">Método GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="f75aa-123">GetTypeFields Method</span></span>](icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="f75aa-124">Obtém um ponteiro para uma matriz que contém informações de campo para um tipo com base em seu identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="f75aa-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="f75aa-125">Método GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="f75aa-125">GetTypeForTypeID Method</span></span>](icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="f75aa-126">Obtém um objeto de tipo que fornece informações sobre um objeto com base em seus identificadores de tipo.</span><span class="sxs-lookup"><span data-stu-id="f75aa-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="f75aa-127">Método GetTypeID</span><span class="sxs-lookup"><span data-stu-id="f75aa-127">GetTypeID Method</span></span>](icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="f75aa-128">Obtém o identificador de tipo para o objeto em um endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="f75aa-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="f75aa-129">Método GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="f75aa-129">GetTypeLayout Method</span></span>](icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="f75aa-130">Obtém informações sobre o layout de um objeto na memória com base em seu identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="f75aa-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f75aa-131">Comentários</span><span class="sxs-lookup"><span data-stu-id="f75aa-131">Remarks</span></span>  

 <span data-ttu-id="f75aa-132">Essa interface estende logicamente as interfaces ICorDebugProcess, ICorDebugProcess2 e [ICorDebugProcess3](icordebugprocess3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f75aa-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f75aa-133">Esta interface não dá suporte a chamadas remotas de outro computador ou de outro processo.</span><span class="sxs-lookup"><span data-stu-id="f75aa-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f75aa-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f75aa-134">Requirements</span></span>  

 <span data-ttu-id="f75aa-135">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f75aa-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f75aa-136">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f75aa-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f75aa-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f75aa-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f75aa-138">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f75aa-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75aa-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="f75aa-139">See also</span></span>

- [<span data-ttu-id="f75aa-140">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="f75aa-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f75aa-141">Depuração</span><span class="sxs-lookup"><span data-stu-id="f75aa-141">Debugging</span></span>](index.md)
