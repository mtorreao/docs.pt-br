---
title: Método ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 29153da86812583a0ea789da0c0816f08e0a6b43
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698072"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="57625-102">Método ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="57625-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>

<span data-ttu-id="57625-103">Obtém o endereço base do módulo carregado.</span><span class="sxs-lookup"><span data-stu-id="57625-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57625-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="57625-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57625-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="57625-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="57625-106">fora Um ponteiro para o endereço base do módulo carregado.</span><span class="sxs-lookup"><span data-stu-id="57625-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57625-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="57625-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57625-108">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="57625-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57625-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57625-109">Requirements</span></span>  

 <span data-ttu-id="57625-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57625-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57625-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57625-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57625-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57625-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57625-113">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57625-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57625-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="57625-114">See also</span></span>

- [<span data-ttu-id="57625-115">Interface ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="57625-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="57625-116">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="57625-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
