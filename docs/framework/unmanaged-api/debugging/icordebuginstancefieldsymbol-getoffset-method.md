---
title: 'Método ICorDebugInstanceFieldSymbol:: GetOffset'
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 2d73de46bbb1023f20dd9023076630611c74be5d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724917"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="7eaad-102">Método ICorDebugInstanceFieldSymbol:: GetOffset</span><span class="sxs-lookup"><span data-stu-id="7eaad-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>

<span data-ttu-id="7eaad-103">Obtém o deslocamento em bytes deste campo de instância em sua classe pai.</span><span class="sxs-lookup"><span data-stu-id="7eaad-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eaad-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7eaad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eaad-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7eaad-105">Parameters</span></span>  

 `pcbOffset`  
 <span data-ttu-id="7eaad-106">Um ponteiro para o número de bytes que esse campo de instância é deslocado em sua classe pai.</span><span class="sxs-lookup"><span data-stu-id="7eaad-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eaad-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="7eaad-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7eaad-108">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7eaad-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eaad-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7eaad-109">Requirements</span></span>  

 <span data-ttu-id="7eaad-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eaad-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eaad-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7eaad-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7eaad-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eaad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eaad-113">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eaad-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eaad-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="7eaad-114">See also</span></span>

- [<span data-ttu-id="7eaad-115">Interface ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="7eaad-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="7eaad-116">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="7eaad-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
