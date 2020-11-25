---
title: Estrutura COR_DEBUG_IL_TO_NATIVE_MAP
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
ms.openlocfilehash: 61544d0dfe876f35fdfbe5afa945fad0620c0eb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726646"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="5e6fc-102">Estrutura COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="5e6fc-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>

<span data-ttu-id="5e6fc-103">Contém os deslocamentos que são usados ​​para mapear o código da MSIL (Microsoft intermediate language) para o código nativo.</span><span class="sxs-lookup"><span data-stu-id="5e6fc-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e6fc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5e6fc-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="5e6fc-105">Membros</span><span class="sxs-lookup"><span data-stu-id="5e6fc-105">Members</span></span>  
  
|<span data-ttu-id="5e6fc-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5e6fc-106">Member</span></span>|<span data-ttu-id="5e6fc-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="5e6fc-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="5e6fc-108">O deslocamento do código MSIL.</span><span class="sxs-lookup"><span data-stu-id="5e6fc-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="5e6fc-109">O deslocamento do início do código nativo.</span><span class="sxs-lookup"><span data-stu-id="5e6fc-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="5e6fc-110">O deslocamento do final do código nativo.</span><span class="sxs-lookup"><span data-stu-id="5e6fc-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e6fc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e6fc-111">Requirements</span></span>  

 <span data-ttu-id="5e6fc-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e6fc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e6fc-113">**Cabeçalho:** CorProf. idl, CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="5e6fc-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="5e6fc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e6fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e6fc-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e6fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6fc-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="5e6fc-116">See also</span></span>

- [<span data-ttu-id="5e6fc-117">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="5e6fc-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="5e6fc-118">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="5e6fc-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="5e6fc-119">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="5e6fc-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="5e6fc-120">Depuração</span><span class="sxs-lookup"><span data-stu-id="5e6fc-120">Debugging</span></span>](index.md)
