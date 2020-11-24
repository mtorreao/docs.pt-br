---
title: 'Método ICorDebugStaticFieldSymbol:: GetSize'
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: 34567247935588363d96b141717d7ec07bb76546
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677203"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="ca8d7-102">Método ICorDebugStaticFieldSymbol:: GetSize</span><span class="sxs-lookup"><span data-stu-id="ca8d7-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="ca8d7-103">Obtém o tamanho em bytes do campo estático.</span><span class="sxs-lookup"><span data-stu-id="ca8d7-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca8d7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ca8d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca8d7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ca8d7-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="ca8d7-106">fora Um ponteiro para o comprimento do campo.</span><span class="sxs-lookup"><span data-stu-id="ca8d7-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca8d7-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="ca8d7-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca8d7-108">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ca8d7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca8d7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca8d7-109">Requirements</span></span>  

 <span data-ttu-id="ca8d7-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca8d7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca8d7-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca8d7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca8d7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca8d7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca8d7-113">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca8d7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca8d7-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="ca8d7-114">See also</span></span>

- [<span data-ttu-id="ca8d7-115">Interface ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="ca8d7-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="ca8d7-116">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="ca8d7-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
