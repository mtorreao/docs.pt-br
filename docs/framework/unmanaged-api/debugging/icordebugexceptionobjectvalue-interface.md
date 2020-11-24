---
title: Interface ICorDebugExceptionObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 6a0c33799b2b2aaa48e3b18b7b4bb37643508bd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678877"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="f4642-102">Interface ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="f4642-102">ICorDebugExceptionObjectValue Interface</span></span>

<span data-ttu-id="f4642-103">Estende a interface "ICorDebugObjectValue" para fornecer informações de rastreamento de pilha de um objeto de exceção gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f4642-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4642-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4642-104">Methods</span></span>  
  
|<span data-ttu-id="f4642-105">Método</span><span class="sxs-lookup"><span data-stu-id="f4642-105">Method</span></span>|<span data-ttu-id="f4642-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f4642-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4642-107">Método EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="f4642-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="f4642-108">Obtém um enumerador para a pilha de chamadas inserido em um objeto de exceção.</span><span class="sxs-lookup"><span data-stu-id="f4642-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4642-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="f4642-109">Remarks</span></span>  

 <span data-ttu-id="f4642-110">A chamada para `QueryInterface` terá sucesso para objetos gerenciados que derivam de <xref:System.Exception?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f4642-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4642-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4642-111">Requirements</span></span>  

 <span data-ttu-id="f4642-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4642-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4642-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4642-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4642-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4642-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4642-115">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4642-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4642-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="f4642-116">See also</span></span>

- [<span data-ttu-id="f4642-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="f4642-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f4642-118">Depuração</span><span class="sxs-lookup"><span data-stu-id="f4642-118">Debugging</span></span>](index.md)
