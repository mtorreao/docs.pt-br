---
title: Método ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: c909b46a9bb70d23d1cd3a769ac24fcf58479308
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713789"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="951e2-102">Método ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="951e2-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>

<span data-ttu-id="951e2-103">Retorna o caminho de um módulo de endereço base do módulo.</span><span class="sxs-lookup"><span data-stu-id="951e2-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951e2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="951e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="951e2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="951e2-105">Parameters</span></span>  

 `baseAddress`  
 <span data-ttu-id="951e2-106">no Um valor [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) que representa o endereço base do módulo.</span><span class="sxs-lookup"><span data-stu-id="951e2-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="951e2-107">[in] O número de caracteres no buffer que receberá o caminho do módulo.</span><span class="sxs-lookup"><span data-stu-id="951e2-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="951e2-108">[out] Um ponteiro para o número de caracteres gravados para o buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="951e2-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="951e2-109">[out] O caminho do módulo.</span><span class="sxs-lookup"><span data-stu-id="951e2-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="951e2-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="951e2-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="951e2-111">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="951e2-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="951e2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="951e2-112">Requirements</span></span>  

 <span data-ttu-id="951e2-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="951e2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="951e2-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="951e2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="951e2-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="951e2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="951e2-116">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="951e2-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="951e2-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="951e2-117">See also</span></span>

- [<span data-ttu-id="951e2-118">Interface ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="951e2-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="951e2-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="951e2-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
