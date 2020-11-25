---
title: 'Método ICorDebugMemoryBuffer:: GetStartAddress'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f76bf1479db987e4956d8b876f67d629d927f956
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710743"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="9c3dd-102">Método ICorDebugMemoryBuffer:: GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="9c3dd-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>

<span data-ttu-id="9c3dd-103">Obtém o endereço inicial do buffer de memória.</span><span class="sxs-lookup"><span data-stu-id="9c3dd-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c3dd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9c3dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c3dd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9c3dd-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="9c3dd-106">fora Um ponteiro para o endereço inicial do buffer de memória.</span><span class="sxs-lookup"><span data-stu-id="9c3dd-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c3dd-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="9c3dd-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="9c3dd-108">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9c3dd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c3dd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c3dd-109">Requirements</span></span>  

 <span data-ttu-id="9c3dd-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c3dd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c3dd-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c3dd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c3dd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c3dd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c3dd-113">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c3dd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c3dd-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="9c3dd-114">See also</span></span>

- [<span data-ttu-id="9c3dd-115">Interface ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="9c3dd-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="9c3dd-116">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="9c3dd-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
