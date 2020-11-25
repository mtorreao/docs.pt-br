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
# <a name="cor_debug_il_to_native_map-structure"></a>Estrutura COR_DEBUG_IL_TO_NATIVE_MAP

Contém os deslocamentos que são usados ​​para mapear o código da MSIL (Microsoft intermediate language) para o código nativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`ilOffset`|O deslocamento do código MSIL.|  
|`nativeStartOffset`|O deslocamento do início do código nativo.|  
|`nativeEndOffset`|O deslocamento do final do código nativo.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorDebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Método GetILToNativeMapping](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [Método GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)
- [Estruturas de depuração](debugging-structures.md)
- [Depuração](index.md)
