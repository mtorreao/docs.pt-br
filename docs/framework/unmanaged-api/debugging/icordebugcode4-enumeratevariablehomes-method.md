---
title: 'Método ICorDebugCode4:: EnumerateVariableHomes'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 6d58efa5629bb02158a275dec61c0313bca821a1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720744"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="06d2a-102">Método ICorDebugCode4:: EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="06d2a-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>

<span data-ttu-id="06d2a-103">Obtém um enumerador para as variáveis locais e argumentos em uma função.</span><span class="sxs-lookup"><span data-stu-id="06d2a-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d2a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="06d2a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06d2a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="06d2a-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="06d2a-106">Um ponteiro para o endereço de um objeto de interface [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) que é um enumerador para as variáveis locais e argumentos em uma função.</span><span class="sxs-lookup"><span data-stu-id="06d2a-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06d2a-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="06d2a-107">Remarks</span></span>  

 <span data-ttu-id="06d2a-108">O objeto de interface [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) é um enumerador padrão derivado da interface "ICorDebugEnum" que permite enumerar objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="06d2a-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="06d2a-109">A coleção pode incluir vários objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) para o mesmo índice de slot ou de argumento se eles tiverem diferentes residências em pontos diferentes na função.</span><span class="sxs-lookup"><span data-stu-id="06d2a-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d2a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06d2a-110">Requirements</span></span>  

 <span data-ttu-id="06d2a-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06d2a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d2a-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06d2a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06d2a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06d2a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06d2a-114">**.NET Framework versões:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d2a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d2a-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="06d2a-115">See also</span></span>

- [<span data-ttu-id="06d2a-116">Interface ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="06d2a-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="06d2a-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="06d2a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
