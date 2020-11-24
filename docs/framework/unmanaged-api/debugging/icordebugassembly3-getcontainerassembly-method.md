---
title: Método ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 51e68e73983425cdd7d648b6856809fcba590f70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688543"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="774ab-102">Método ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="774ab-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>

<span data-ttu-id="774ab-103">Retorna o assembly do contêiner desse objeto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="774ab-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="774ab-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="774ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="774ab-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="774ab-105">Parameters</span></span>  

 `ppAssembly`  
 <span data-ttu-id="774ab-106">Um ponteiro para o endereço de um objeto ICorDebugAssembly que representa o assembly do contêiner ou **nulo** se a chamada do método falhar.</span><span class="sxs-lookup"><span data-stu-id="774ab-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="774ab-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="774ab-107">Return Value</span></span>  

 <span data-ttu-id="774ab-108">`S_OK` se a chamada do método for concluída com sucesso; caso contrário, `S_FALSE` , e `ppAssembly` será **nulo**.</span><span class="sxs-lookup"><span data-stu-id="774ab-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="774ab-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="774ab-109">Remarks</span></span>  

 <span data-ttu-id="774ab-110">Se esse assembly foi mesclado com outros dentro de um assembly de contêiner único, esse método retorna o assembly do contêiner.</span><span class="sxs-lookup"><span data-stu-id="774ab-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="774ab-111">Para obter mais informações e terminologia, consulte o tópico [ICorDebugProcess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="774ab-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="774ab-112">Esse método está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="774ab-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="774ab-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="774ab-113">Requirements</span></span>  

 <span data-ttu-id="774ab-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="774ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="774ab-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="774ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="774ab-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="774ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="774ab-117">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="774ab-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="774ab-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="774ab-118">See also</span></span>

- [<span data-ttu-id="774ab-119">Interface ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="774ab-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="774ab-120">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="774ab-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
