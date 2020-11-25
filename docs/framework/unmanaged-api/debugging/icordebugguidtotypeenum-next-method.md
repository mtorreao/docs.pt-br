---
title: Método ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 68f548705213da7d715ae569116abae0cd24129d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705651"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="49ab4-102">Método ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="49ab4-102">ICorDebugGuidToTypeEnum::Next Method</span></span>

<span data-ttu-id="49ab4-103">Obtém o número especificado de instâncias de [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) que MAPEIAm GUIDs para informações de tipo.</span><span class="sxs-lookup"><span data-stu-id="49ab4-103">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49ab4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="49ab4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49ab4-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="49ab4-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="49ab4-106">no O número de objetos de mapeamento GUID-to-Type a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="49ab4-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="49ab4-107">fora Uma matriz de ponteiros, cada um dos quais aponta para um objeto [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) que MAPEIA um GUID de Windows Runtime para seu objeto ICorDebugType correspondente.</span><span class="sxs-lookup"><span data-stu-id="49ab4-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="49ab4-108">fora Um ponteiro para o número de objetos [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) realmente retornados em `values` .</span><span class="sxs-lookup"><span data-stu-id="49ab4-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49ab4-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="49ab4-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49ab4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49ab4-110">Requirements</span></span>  

 <span data-ttu-id="49ab4-111">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="49ab4-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="49ab4-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49ab4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49ab4-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49ab4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49ab4-114">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49ab4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ab4-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="49ab4-115">See also</span></span>

- [<span data-ttu-id="49ab4-116">Interface ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="49ab4-116">ICorDebugGuidToTypeEnum Interface</span></span>](icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="49ab4-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="49ab4-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
