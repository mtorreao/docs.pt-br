---
title: Interface ICorDebugStringValue
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
ms.openlocfilehash: cd6c5726b9a938d04cf4eb018ec9851c81d9c745
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697043"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="f647e-102">Interface ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="f647e-102">ICorDebugStringValue Interface</span></span>

<span data-ttu-id="f647e-103">Uma subclasse de ICorDebugHeapValue que se aplica a valores de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f647e-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f647e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f647e-104">Methods</span></span>  
  
|<span data-ttu-id="f647e-105">Método</span><span class="sxs-lookup"><span data-stu-id="f647e-105">Method</span></span>|<span data-ttu-id="f647e-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f647e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f647e-107">Método GetLength</span><span class="sxs-lookup"><span data-stu-id="f647e-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="f647e-108">Obtém o número de caracteres na cadeia de caracteres referenciada por isso `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="f647e-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="f647e-109">Método GetString</span><span class="sxs-lookup"><span data-stu-id="f647e-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="f647e-110">Obtém a cadeia de caracteres referenciada por isso `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="f647e-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f647e-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="f647e-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f647e-112">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="f647e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f647e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f647e-113">Requirements</span></span>  

 <span data-ttu-id="f647e-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f647e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f647e-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f647e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f647e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f647e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f647e-117">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f647e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f647e-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="f647e-118">See also</span></span>

- [<span data-ttu-id="f647e-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="f647e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
