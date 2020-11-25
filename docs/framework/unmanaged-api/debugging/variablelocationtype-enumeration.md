---
title: Enumeração VariableLocationType
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: 1c65efa006a8b2f4fb4db257b4ad2cde99c4e75e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725255"
---
# <a name="variablelocationtype-enumeration"></a>Enumeração VariableLocationType

Indica o tipo de local nativo de uma variável.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`VLT_REGISTER`|A variável está em um registro.|  
|`VLT_REGISTER_RELATIVE`|A variável está em um local de memória relativa ao registro.|  
|`VLT_INVALID`|A variável não é armazenada em um local de memória de registro ou de registro relativo.|  
  
## <a name="remarks"></a>Comentários  

 Um membro da `VariableLocationType` enumeração é retornado pelo método [ICorDebugVariableHome:: getlocationtype](icordebugvariablehome-getlocationtype-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Declarando enumerações](debugging-enumerations.md)
