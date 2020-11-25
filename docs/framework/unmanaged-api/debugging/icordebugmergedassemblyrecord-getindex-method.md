---
title: 'Método ICorDebugMergedAssemblyRecord:: GetIndex'
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 3056d22f5ddc1b11b79ee072aba68ce3ad40e8da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710630"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="f2dcc-102">Método ICorDebugMergedAssemblyRecord:: GetIndex</span><span class="sxs-lookup"><span data-stu-id="f2dcc-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>

<span data-ttu-id="f2dcc-103">Obtém o índice de prefixo do assembly.</span><span class="sxs-lookup"><span data-stu-id="f2dcc-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2dcc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f2dcc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2dcc-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f2dcc-105">Parameters</span></span>  

 `pIndex`  
 <span data-ttu-id="f2dcc-106">fora Um ponteiro para o índice de prefixo.</span><span class="sxs-lookup"><span data-stu-id="f2dcc-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2dcc-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="f2dcc-107">Remarks</span></span>  

 <span data-ttu-id="f2dcc-108">O índice de prefixo é usado para evitar colisões de nome nos nomes de tipos de metadados mesclados.</span><span class="sxs-lookup"><span data-stu-id="f2dcc-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2dcc-109">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f2dcc-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2dcc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2dcc-110">Requirements</span></span>  

 <span data-ttu-id="f2dcc-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2dcc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2dcc-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2dcc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2dcc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2dcc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2dcc-114">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2dcc-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2dcc-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="f2dcc-115">See also</span></span>

- [<span data-ttu-id="f2dcc-116">Interface ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="f2dcc-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="f2dcc-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="f2dcc-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
