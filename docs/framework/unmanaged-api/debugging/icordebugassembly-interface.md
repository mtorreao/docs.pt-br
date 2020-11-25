---
title: Interface ICorDebugAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: 821eae8ea5b4147408e9fe60d1e5b70c7936959e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696239"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="03d8e-102">Interface ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="03d8e-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="03d8e-103">Representa um assembly.</span><span class="sxs-lookup"><span data-stu-id="03d8e-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03d8e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="03d8e-104">Methods</span></span>  
  
|<span data-ttu-id="03d8e-105">Método</span><span class="sxs-lookup"><span data-stu-id="03d8e-105">Method</span></span>|<span data-ttu-id="03d8e-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="03d8e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03d8e-107">Método EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="03d8e-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="03d8e-108">Obtém um enumerador para os módulos contidos no assembly.</span><span class="sxs-lookup"><span data-stu-id="03d8e-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="03d8e-109">Método GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="03d8e-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="03d8e-110">Obtém um ponteiro de interface para o domínio do aplicativo que contém essa `ICorDebugAssembly` instância.</span><span class="sxs-lookup"><span data-stu-id="03d8e-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="03d8e-111">Método GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="03d8e-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="03d8e-112">Não implementado na versão atual do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03d8e-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="03d8e-113">Método GetName</span><span class="sxs-lookup"><span data-stu-id="03d8e-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="03d8e-114">Obtém o nome do assembly.</span><span class="sxs-lookup"><span data-stu-id="03d8e-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="03d8e-115">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="03d8e-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="03d8e-116">Obtém a instância ICorDebugProcess na qual o assembly está em execução.</span><span class="sxs-lookup"><span data-stu-id="03d8e-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03d8e-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="03d8e-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03d8e-118">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="03d8e-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03d8e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03d8e-119">Requirements</span></span>  

 <span data-ttu-id="03d8e-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03d8e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03d8e-121">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03d8e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03d8e-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03d8e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03d8e-123">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03d8e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d8e-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="03d8e-124">See also</span></span>

- [<span data-ttu-id="03d8e-125">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="03d8e-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
