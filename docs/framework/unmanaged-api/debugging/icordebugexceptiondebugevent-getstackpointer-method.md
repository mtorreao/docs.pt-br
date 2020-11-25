---
title: 'Método ICorDebugExceptionDebugEvent:: GetStackPointer'
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 46906e7d3ce7f257eb776e50dc6097946eb77d1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697396"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="f59ac-102">Método ICorDebugExceptionDebugEvent:: GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="f59ac-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>

<span data-ttu-id="f59ac-103">Obtém o ponteiro de pilha para este evento de depuração de exceção.</span><span class="sxs-lookup"><span data-stu-id="f59ac-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f59ac-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f59ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f59ac-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f59ac-105">Parameters</span></span>  

 `pStackPointer`  
 <span data-ttu-id="f59ac-106">fora Um ponteiro para o endereço do ponteiro de pilha para este evento de depuração de exceção.</span><span class="sxs-lookup"><span data-stu-id="f59ac-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="f59ac-107">Consulte a seção Comentários para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f59ac-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f59ac-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="f59ac-108">Remarks</span></span>  

 <span data-ttu-id="f59ac-109">O significado desse ponteiro de pilha depende do tipo de evento, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f59ac-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="f59ac-110">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="f59ac-110">Event type</span></span>|<span data-ttu-id="f59ac-111">Significado do `pStackPointer` valor</span><span class="sxs-lookup"><span data-stu-id="f59ac-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="f59ac-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="f59ac-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="f59ac-113">O ponteiro de pilha para o quadro que gerou a exceção.</span><span class="sxs-lookup"><span data-stu-id="f59ac-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="f59ac-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="f59ac-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="f59ac-115">O ponteiro de pilha para o quadro de código do usuário mais próximo do ponto da exceção gerada.</span><span class="sxs-lookup"><span data-stu-id="f59ac-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="f59ac-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="f59ac-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="f59ac-117">O ponteiro de pilha para o quadro que contém o manipulador catch.</span><span class="sxs-lookup"><span data-stu-id="f59ac-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="f59ac-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="f59ac-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="f59ac-119">`pStackPointer` é **nulo**.</span><span class="sxs-lookup"><span data-stu-id="f59ac-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f59ac-120">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f59ac-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="f59ac-121">O tipo de evento está disponível no método [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f59ac-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f59ac-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f59ac-122">Requirements</span></span>  

 <span data-ttu-id="f59ac-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f59ac-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f59ac-124">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f59ac-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f59ac-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f59ac-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f59ac-126">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f59ac-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f59ac-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="f59ac-127">See also</span></span>

- [<span data-ttu-id="f59ac-128">Interface ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="f59ac-128">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="f59ac-129">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="f59ac-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
