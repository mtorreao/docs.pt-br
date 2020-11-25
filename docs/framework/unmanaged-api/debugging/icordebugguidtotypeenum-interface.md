---
title: Interface ICorDebugGuidToTypeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: 149c5b09639c8809e736ade09566e7b1b530e3eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705703"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="0d182-102">Interface ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="0d182-102">ICorDebugGuidToTypeEnum Interface</span></span>

<span data-ttu-id="0d182-103">Fornece um enumerador que define o mapeamento entre um conjunto de GUIDs e seus tipos correspondentes, que são representados por instâncias de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="0d182-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="0d182-104">Essa interface herda os métodos da interface ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="0d182-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d182-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0d182-105">Methods</span></span>  
  
|<span data-ttu-id="0d182-106">Método</span><span class="sxs-lookup"><span data-stu-id="0d182-106">Method</span></span>|<span data-ttu-id="0d182-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0d182-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d182-108">ICorDebugGuidToTypeEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="0d182-108">ICorDebugGuidToTypeEnum::Next</span></span>](icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="0d182-109">Obtém o número especificado de instâncias de [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) que MAPEIAm GUIDs para informações de tipo.</span><span class="sxs-lookup"><span data-stu-id="0d182-109">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d182-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="0d182-110">Remarks</span></span>  

 <span data-ttu-id="0d182-111">Um `ICorDebugGuidToTypeEnum` objeto de interface pode ser recuperado chamando o método [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0d182-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="0d182-112">Um depurador pode chamar o [próximo](icordebugguidtotypeenum-next-method.md) método da interface para recuperar objetos [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) que representam mapeamentos de representações gerenciadas de tipos de Windows Runtime carregados no domínio de aplicativo usado para a chamada para o método [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0d182-112">A debugger can call this interface's [Next](icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d182-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d182-113">Requirements</span></span>  

 <span data-ttu-id="0d182-114">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="0d182-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="0d182-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d182-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d182-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d182-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d182-117">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d182-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d182-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="0d182-118">See also</span></span>

- [<span data-ttu-id="0d182-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="0d182-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
