---
title: Interface ICorDebugAppDomain2
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: f20ae6977504f958b7bfa8e2f073b7db6e8b822b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731469"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="0c421-102">Interface ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="0c421-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="0c421-103">Fornece métodos para trabalhar com matrizes, ponteiros, ponteiros de função e tipos de referência.</span><span class="sxs-lookup"><span data-stu-id="0c421-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="0c421-104">Essa interface é uma extensão da interface ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="0c421-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c421-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0c421-105">Methods</span></span>  
  
|<span data-ttu-id="0c421-106">Método</span><span class="sxs-lookup"><span data-stu-id="0c421-106">Method</span></span>|<span data-ttu-id="0c421-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0c421-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c421-108">Método GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="0c421-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="0c421-109">Obtém uma matriz do tipo especificado ou um ponteiro ou uma referência para o tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="0c421-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="0c421-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="0c421-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="0c421-111">Obtém um ponteiro para uma função que tem uma determinada assinatura.</span><span class="sxs-lookup"><span data-stu-id="0c421-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c421-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="0c421-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c421-113">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="0c421-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c421-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c421-114">Requirements</span></span>  

 <span data-ttu-id="0c421-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c421-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c421-116">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c421-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c421-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c421-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c421-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c421-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c421-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c421-119">See also</span></span>

- [<span data-ttu-id="0c421-120">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="0c421-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
