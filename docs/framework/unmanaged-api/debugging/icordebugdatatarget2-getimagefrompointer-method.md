---
title: Método ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 41385fe915733f052af67c82d984c8b9d853c579
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713815"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="43cb6-102">Método ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="43cb6-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>

<span data-ttu-id="43cb6-103">Retorna o endereço base do módulo e o tamanho de um endereço no módulo.</span><span class="sxs-lookup"><span data-stu-id="43cb6-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43cb6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="43cb6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43cb6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="43cb6-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="43cb6-106">Um valor [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) que representa um endereço em um módulo.</span><span class="sxs-lookup"><span data-stu-id="43cb6-106">A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="43cb6-107">fora Um valor [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) que representa o endereço base do módulo.</span><span class="sxs-lookup"><span data-stu-id="43cb6-107">[out] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="43cb6-108">Um ponteiro para o tamanho do módulo.</span><span class="sxs-lookup"><span data-stu-id="43cb6-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43cb6-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="43cb6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43cb6-110">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="43cb6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43cb6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43cb6-111">Requirements</span></span>  

 <span data-ttu-id="43cb6-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43cb6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43cb6-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43cb6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43cb6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43cb6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43cb6-115">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43cb6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43cb6-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="43cb6-116">See also</span></span>

- [<span data-ttu-id="43cb6-117">Interface ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="43cb6-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="43cb6-118">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="43cb6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
