---
title: Interface ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: 4f488741f4233f06c128e0a262ce798ef27af3ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699619"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="08bc3-102">Interface ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="08bc3-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="08bc3-103">Representa um tipo, que pode ser básico ou complexo (isto é, definido pelo usuário).</span><span class="sxs-lookup"><span data-stu-id="08bc3-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="08bc3-104">Se o tipo for genérico, `ICorDebugClass` representará o tipo genérico sem instância.</span><span class="sxs-lookup"><span data-stu-id="08bc3-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08bc3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="08bc3-105">Methods</span></span>  
  
|<span data-ttu-id="08bc3-106">Método</span><span class="sxs-lookup"><span data-stu-id="08bc3-106">Method</span></span>|<span data-ttu-id="08bc3-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="08bc3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08bc3-108">Método GetModule</span><span class="sxs-lookup"><span data-stu-id="08bc3-108">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="08bc3-109">Obtém o módulo que define essa classe.</span><span class="sxs-lookup"><span data-stu-id="08bc3-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="08bc3-110">Método GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="08bc3-110">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="08bc3-111">Obtém o valor do campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="08bc3-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="08bc3-112">Método GetToken</span><span class="sxs-lookup"><span data-stu-id="08bc3-112">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="08bc3-113">Obtém o `TypeDef` token de metadados para esta classe.</span><span class="sxs-lookup"><span data-stu-id="08bc3-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08bc3-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="08bc3-114">Remarks</span></span>  

 <span data-ttu-id="08bc3-115">A `ICorDebugClass` interface representa um tipo genérico não instanciado.</span><span class="sxs-lookup"><span data-stu-id="08bc3-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="08bc3-116">A interface ICorDebugType representa um tipo genérico instanciado.</span><span class="sxs-lookup"><span data-stu-id="08bc3-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="08bc3-117">Por exemplo, `Hashtable<K, V>` seria representado pelo `ICorDebugClass` , enquanto `Hashtable<Int32, String>` seria representado por `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="08bc3-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="08bc3-118">Tipos não genéricos são representados por `ICorDebugClass` e `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="08bc3-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="08bc3-119">A última interface foi introduzida no .NET Framework versão 2,0 para lidar com a instanciação de tipo.</span><span class="sxs-lookup"><span data-stu-id="08bc3-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08bc3-120">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="08bc3-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08bc3-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08bc3-121">Requirements</span></span>  

 <span data-ttu-id="08bc3-122">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08bc3-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08bc3-123">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08bc3-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08bc3-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08bc3-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08bc3-125">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08bc3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08bc3-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="08bc3-126">See also</span></span>

- [<span data-ttu-id="08bc3-127">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="08bc3-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
