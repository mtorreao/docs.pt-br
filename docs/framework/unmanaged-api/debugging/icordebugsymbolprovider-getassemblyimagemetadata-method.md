---
title: 'Método ICorDebugSymbolProvider:: GetAssemblyImageMetadata'
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 9644d1323660730d210bd0305c2785fce4174455
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709135"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="b9f84-102">Método ICorDebugSymbolProvider:: GetAssemblyImageMetadata</span><span class="sxs-lookup"><span data-stu-id="b9f84-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>

<span data-ttu-id="b9f84-103">Retorna os metadados de um assembly mesclado.</span><span class="sxs-lookup"><span data-stu-id="b9f84-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f84-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b9f84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9f84-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b9f84-105">Parameters</span></span>  

 `ppMemoryBuffer`  
 <span data-ttu-id="b9f84-106">fora Um ponteiro para o endereço de um objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contém informações sobre o tamanho e o endereço dos metadados do assembly mesclado.</span><span class="sxs-lookup"><span data-stu-id="b9f84-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9f84-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="b9f84-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9f84-108">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b9f84-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f84-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9f84-109">Requirements</span></span>  

 <span data-ttu-id="b9f84-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f84-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f84-111">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9f84-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9f84-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9f84-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9f84-113">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f84-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f84-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9f84-114">See also</span></span>

- [<span data-ttu-id="b9f84-115">Interface ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="b9f84-115">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b9f84-116">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="b9f84-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
