---
title: Método ICorDebugCode::GetILToNativeMapping
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
ms.openlocfilehash: 0adb9e58ca2c6b5b430a0413fa11ba59d79a0539
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688101"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="39f16-102">Método ICorDebugCode::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="39f16-102">ICorDebugCode::GetILToNativeMapping Method</span></span>

<span data-ttu-id="39f16-103">Obtém uma matriz de instâncias "COR_DEBUG_IL_TO_NATIVE_MAP" que representam mapeamentos de deslocamentos de MSIL (Microsoft Intermediate Language) para deslocamentos nativos.</span><span class="sxs-lookup"><span data-stu-id="39f16-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f16-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="39f16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39f16-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="39f16-105">Parameters</span></span>  

 `cMap`  
 <span data-ttu-id="39f16-106">no O tamanho da `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="39f16-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="39f16-107">fora Um ponteiro para o número real de elementos retornados na `map` matriz.</span><span class="sxs-lookup"><span data-stu-id="39f16-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="39f16-108">fora Uma matriz de `COR_DEBUG_IL_TO_NATIVE_MAP` estruturas, cada uma representando um mapeamento de um deslocamento de MSIL para um deslocamento nativo.</span><span class="sxs-lookup"><span data-stu-id="39f16-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="39f16-109">Não há nenhuma ordem para a matriz de elementos retornada.</span><span class="sxs-lookup"><span data-stu-id="39f16-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39f16-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="39f16-110">Remarks</span></span>  

 <span data-ttu-id="39f16-111">O `GetILToNativeMapping` método retornará resultados significativos somente se essa instância "ICorDebugCode" representar o código nativo que era JIT (just-in-time) compilado do código MSIL.</span><span class="sxs-lookup"><span data-stu-id="39f16-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39f16-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39f16-112">Requirements</span></span>  

 <span data-ttu-id="39f16-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39f16-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39f16-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39f16-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39f16-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39f16-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39f16-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39f16-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f16-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="39f16-117">See also</span></span>

- [<span data-ttu-id="39f16-118">Interface ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="39f16-118">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
