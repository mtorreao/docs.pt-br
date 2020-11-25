---
title: Enumeração CorDebugIlToNativeMappingTypes
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
ms.openlocfilehash: ecb88195e3ecc7c540679a683005798247afe57f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712398"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a>Enumeração CorDebugIlToNativeMappingTypes

Indica se um intervalo específico de instruções nativas, representado por uma instância da estrutura COR_DEBUG_IL_TO_NATIVE_MAP, corresponde a uma região de código especial.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`NO_MAPPING`|O intervalo de instruções nativas não corresponde a nenhuma região de código especial.|  
|`PROLOG`|O intervalo de instruções nativas corresponde ao prólogo.|  
|`EPILOG`|O intervalo de instruções nativas corresponde ao epílogo.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Método GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)
- [Declarando enumerações](debugging-enumerations.md)
