---
title: 'Método ICorDebugVariableSymbol:: GetSlotIndex'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: fc42517cb95dfc14c472b5bb9111ebd70639cee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725983"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="758eb-102">Método ICorDebugVariableSymbol:: GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="758eb-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>

<span data-ttu-id="758eb-103">Obtém o índice de slot gerenciado de uma variável local.</span><span class="sxs-lookup"><span data-stu-id="758eb-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758eb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="758eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="758eb-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="758eb-105">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="758eb-106">fora Um ponteiro para o índice de slot da variável local.</span><span class="sxs-lookup"><span data-stu-id="758eb-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="758eb-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="758eb-107">Return Value</span></span>  

 <span data-ttu-id="758eb-108">`S_OK` se bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="758eb-108">`S_OK` if successful.</span></span> <span data-ttu-id="758eb-109">`E_FAIL` se a variável for um argumento de função.</span><span class="sxs-lookup"><span data-stu-id="758eb-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="758eb-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="758eb-110">Remarks</span></span>  

 <span data-ttu-id="758eb-111">O índice de slot gerenciado de uma variável local pode ser usado para recuperar as informações de metadados da variável</span><span class="sxs-lookup"><span data-stu-id="758eb-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="758eb-112">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="758eb-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="758eb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="758eb-113">Requirements</span></span>  

 <span data-ttu-id="758eb-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="758eb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="758eb-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="758eb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="758eb-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="758eb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="758eb-117">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="758eb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="758eb-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="758eb-118">See also</span></span>

- [<span data-ttu-id="758eb-119">Interface ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="758eb-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="758eb-120">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="758eb-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
