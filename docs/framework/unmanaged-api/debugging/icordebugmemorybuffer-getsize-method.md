---
title: 'Método ICorDebugMemoryBuffer:: GetSize'
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7f5458dd12ca83c1a5190bbf7fab0f8e5d06a0e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710742"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="ea5d6-102">Método ICorDebugMemoryBuffer:: GetSize</span><span class="sxs-lookup"><span data-stu-id="ea5d6-102">ICorDebugMemoryBuffer::GetSize Method</span></span>

<span data-ttu-id="ea5d6-103">Obtém o tamanho do buffer de memória em bytes.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5d6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ea5d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea5d6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ea5d6-105">Parameters</span></span>  

 `pcbBufferLength`  
 <span data-ttu-id="ea5d6-106">fora Um ponteiro para o tamanho do buffer de memória.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea5d6-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="ea5d6-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea5d6-108">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea5d6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea5d6-109">Requirements</span></span>  

 <span data-ttu-id="ea5d6-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea5d6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea5d6-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea5d6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea5d6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea5d6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea5d6-113">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5d6-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea5d6-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="ea5d6-114">See also</span></span>

- [<span data-ttu-id="ea5d6-115">Interface ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="ea5d6-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="ea5d6-116">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="ea5d6-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
