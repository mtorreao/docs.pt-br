---
title: 'Método ICorDebugStaticFieldSymbol:: GetAddress'
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: e9404b429ad4507acb5132a86af5f287dbcf07b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677278"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="e9fbc-102">Método ICorDebugStaticFieldSymbol:: GetAddress</span><span class="sxs-lookup"><span data-stu-id="e9fbc-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>

<span data-ttu-id="e9fbc-103">Obtém o endereço de um campo estático.</span><span class="sxs-lookup"><span data-stu-id="e9fbc-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9fbc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e9fbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9fbc-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e9fbc-105">Parameters</span></span>  

 <span data-ttu-id="e9fbc-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="e9fbc-106">pRVA</span></span>  
 <span data-ttu-id="e9fbc-107">fora Um ponteiro para o endereço virtual relativo (RVA) do campo estático.</span><span class="sxs-lookup"><span data-stu-id="e9fbc-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9fbc-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="e9fbc-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9fbc-109">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e9fbc-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9fbc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9fbc-110">Requirements</span></span>  

 <span data-ttu-id="e9fbc-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9fbc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9fbc-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9fbc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9fbc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9fbc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9fbc-114">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9fbc-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9fbc-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="e9fbc-115">See also</span></span>

- [<span data-ttu-id="e9fbc-116">Interface ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e9fbc-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="e9fbc-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="e9fbc-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
