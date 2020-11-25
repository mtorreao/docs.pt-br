---
title: Interface ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: 2a5a618491bf2c624669728d97a690cca315bff8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724670"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="dc432-102">Interface ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="dc432-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="dc432-103">Uma subclasse de "ICorDebugValue" que representa um valor que contém um objeto.</span><span class="sxs-lookup"><span data-stu-id="dc432-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc432-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dc432-104">Methods</span></span>  
  
|<span data-ttu-id="dc432-105">Método</span><span class="sxs-lookup"><span data-stu-id="dc432-105">Method</span></span>|<span data-ttu-id="dc432-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="dc432-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc432-107">Método GetClass</span><span class="sxs-lookup"><span data-stu-id="dc432-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="dc432-108">Obtém um ponteiro de interface para o Common Language Runtime (CLR) <xref:System.Type> do objeto ao qual este `ICorDebugObjectValue` faz referência.</span><span class="sxs-lookup"><span data-stu-id="dc432-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="dc432-109">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="dc432-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="dc432-110">Não implementado.</span><span class="sxs-lookup"><span data-stu-id="dc432-110">Not implemented.</span></span>|  
|[<span data-ttu-id="dc432-111">Método GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="dc432-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="dc432-112">Obtém um ponteiro de interface para um [ICorDebugValue](icordebugvalue-interface.md) que representa o valor do campo especificado da classe especificada.</span><span class="sxs-lookup"><span data-stu-id="dc432-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="dc432-113">Método GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="dc432-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="dc432-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="dc432-114">Obsolete.</span></span> <span data-ttu-id="dc432-115">Não chame esse método.</span><span class="sxs-lookup"><span data-stu-id="dc432-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="dc432-116">Método GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="dc432-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="dc432-117">Não implementado.</span><span class="sxs-lookup"><span data-stu-id="dc432-117">Not implemented.</span></span>|  
|[<span data-ttu-id="dc432-118">Método IsValueClass</span><span class="sxs-lookup"><span data-stu-id="dc432-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="dc432-119">Obtém um valor que indica se o objeto referenciado por este `ICorDebugObjectValue` é um tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="dc432-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="dc432-120">Método SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="dc432-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="dc432-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="dc432-121">Obsolete.</span></span> <span data-ttu-id="dc432-122">Não chame esse método.</span><span class="sxs-lookup"><span data-stu-id="dc432-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc432-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="dc432-123">Remarks</span></span>  

 <span data-ttu-id="dc432-124">Um `ICorDebugObjectValue` permanece válido até que o processo que está sendo depurado seja continuado.</span><span class="sxs-lookup"><span data-stu-id="dc432-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc432-125">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="dc432-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc432-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc432-126">Requirements</span></span>  

 <span data-ttu-id="dc432-127">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc432-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc432-128">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc432-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc432-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc432-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc432-130">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc432-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc432-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="dc432-131">See also</span></span>

- [<span data-ttu-id="dc432-132">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="dc432-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
