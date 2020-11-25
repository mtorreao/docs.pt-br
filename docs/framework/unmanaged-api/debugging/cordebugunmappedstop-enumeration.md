---
title: Enumeração CorDebugUnmappedStop
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: e251bf67adcaf2bbd6565eda068d487eb0d70efd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725762"
---
# <a name="cordebugunmappedstop-enumeration"></a>Enumeração CorDebugUnmappedStop

Especifica o tipo de código não mapeado que pode disparar uma interrupção na execução do código pelo passador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`STOP_NONE`|Não pare em nenhum tipo de código não mapeado.|  
|`STOP_PROLOG`|Parar no código de prólogo.|  
|`STOP_EPILOG`|Pare no código epílogo.|  
|`STOP_NO_MAPPING_INFO`|Pare no código que não tem informações de mapeamento.|  
|`STOP_OTHER_UNMAPPED`|Pare no código não mapeado que não caiba nas categorias prólogo, epílogo, no-Mapping-Information ou unmanaged.|  
|`STOP_UNMANAGED`|Parar em código não gerenciado. Esse valor é válido somente com depuração de interoperabilidade.|  
|`STOP_ALL`|Parar em todos os tipos de código não mapeado.|  
  
## <a name="remarks"></a>Comentários  

 Use o método [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) para definir os sinalizadores que especificam o código não mapeado no qual o stepper será interrompido.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Declarando enumerações](debugging-enumerations.md)
