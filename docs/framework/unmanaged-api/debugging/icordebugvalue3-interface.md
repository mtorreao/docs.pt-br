---
title: Interface ICorDebugValue3
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 419efc7f21f4ac2e68657b2a4d69a8690a2938d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722304"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="8d54a-102">Interface ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="8d54a-102">ICorDebugValue3 Interface</span></span>

<span data-ttu-id="8d54a-103">Estende as interfaces "ICorDebugValue" e "ICorDebugValue2" para fornecer suporte a matrizes com mais de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="8d54a-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d54a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8d54a-104">Methods</span></span>  
  
|<span data-ttu-id="8d54a-105">Método</span><span class="sxs-lookup"><span data-stu-id="8d54a-105">Method</span></span>|<span data-ttu-id="8d54a-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8d54a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d54a-107">Método GetSize64</span><span class="sxs-lookup"><span data-stu-id="8d54a-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="8d54a-108">Obtém o tamanho, em bytes, deste `ICorDebugValue3` objeto.</span><span class="sxs-lookup"><span data-stu-id="8d54a-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d54a-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="8d54a-109">Remarks</span></span>  

 <span data-ttu-id="8d54a-110">O método [ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) retorna um tamanho de objeto que varia de 0 a 2.147.483.647 bytes.</span><span class="sxs-lookup"><span data-stu-id="8d54a-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="8d54a-111">No .NET Framework 4,5, o tamanho das matrizes pode exceder 2 GB.</span><span class="sxs-lookup"><span data-stu-id="8d54a-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="8d54a-112">A `ICorDebugValue3` interface permite que você determine o tamanho dessas matrizes.</span><span class="sxs-lookup"><span data-stu-id="8d54a-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d54a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d54a-113">Requirements</span></span>  

 <span data-ttu-id="8d54a-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d54a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d54a-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d54a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d54a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d54a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d54a-117">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d54a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d54a-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="8d54a-118">See also</span></span>

- [<span data-ttu-id="8d54a-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="8d54a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8d54a-120">Depuração</span><span class="sxs-lookup"><span data-stu-id="8d54a-120">Debugging</span></span>](index.md)
