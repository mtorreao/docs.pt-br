---
title: Método ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 5a5ccaeb36dcda82c0189026e19c6a7c023f3e1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713763"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="fca23-102">Método ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="fca23-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>

<span data-ttu-id="fca23-103">Retorna o provedor de símbolo para um módulo do endereço base do módulo.</span><span class="sxs-lookup"><span data-stu-id="fca23-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fca23-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fca23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fca23-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="fca23-105">Parameters</span></span>  

 `imageBaseAddress`  
 <span data-ttu-id="fca23-106">no Um valor [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) que representa o endereço base de um módulo.</span><span class="sxs-lookup"><span data-stu-id="fca23-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="fca23-107">fora Um ponteiro para o endereço de um objeto [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fca23-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fca23-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="fca23-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fca23-109">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fca23-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fca23-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fca23-110">Requirements</span></span>  

 <span data-ttu-id="fca23-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fca23-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fca23-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fca23-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fca23-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fca23-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fca23-114">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fca23-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca23-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="fca23-115">See also</span></span>

- [<span data-ttu-id="fca23-116">Interface ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="fca23-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="fca23-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="fca23-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
