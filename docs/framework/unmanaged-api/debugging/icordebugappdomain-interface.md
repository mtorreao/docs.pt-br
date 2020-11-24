---
title: Método ICorDebugAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
ms.openlocfilehash: 98273a5d4602c023863758045bdb2a6a502ba7a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687223"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="3f345-102">Método ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="3f345-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="3f345-103">Fornece métodos para depurar domínios de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="3f345-104">Essa interface é uma subclasse de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="3f345-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f345-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3f345-105">Methods</span></span>  
  
|<span data-ttu-id="3f345-106">Método</span><span class="sxs-lookup"><span data-stu-id="3f345-106">Method</span></span>|<span data-ttu-id="3f345-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="3f345-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f345-108">Método Attach</span><span class="sxs-lookup"><span data-stu-id="3f345-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="3f345-109">Anexa o depurador ao domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="3f345-110">Método EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="3f345-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="3f345-111">Obtém um enumerador para os assemblies no domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="3f345-112">Método EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="3f345-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="3f345-113">Obtém um enumerador para todos os pontos de interrupção ativos no domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="3f345-114">Método EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="3f345-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="3f345-115">Obtém um enumerador para todos os percorridos ativos no domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="3f345-116">Método GetId</span><span class="sxs-lookup"><span data-stu-id="3f345-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="3f345-117">Obtém a ID exclusiva do domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="3f345-118">Método GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="3f345-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="3f345-119">Obtém o objeto ICorDebugModule com a interface de metadados fornecida.</span><span class="sxs-lookup"><span data-stu-id="3f345-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="3f345-120">Método GetName</span><span class="sxs-lookup"><span data-stu-id="3f345-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="3f345-121">Obtém o nome do domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="3f345-122">Método GetObject</span><span class="sxs-lookup"><span data-stu-id="3f345-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="3f345-123">Obtém um ponteiro de interface para o domínio do aplicativo Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3f345-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="3f345-124">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="3f345-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="3f345-125">Obtém o processo que contém o domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="3f345-126">Método IsAttached</span><span class="sxs-lookup"><span data-stu-id="3f345-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="3f345-127">Determina se o depurador está anexado ao domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f345-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f345-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="3f345-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f345-129">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="3f345-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f345-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f345-130">Requirements</span></span>  

 <span data-ttu-id="3f345-131">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f345-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f345-132">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f345-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f345-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f345-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f345-134">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f345-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f345-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="3f345-135">See also</span></span>

- [<span data-ttu-id="3f345-136">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="3f345-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
