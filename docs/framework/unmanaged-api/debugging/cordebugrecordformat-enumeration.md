---
title: Enumeração CorDebugRecordFormat
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
ms.openlocfilehash: b3a22d7b32eb258263d373ae91b3fb7fbc9aae99
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696382"
---
# <a name="cordebugrecordformat-enumeration"></a>Enumeração CorDebugRecordFormat

Descreve o formato dos dados em uma matriz de bytes que contém informações sobre um evento de depuração de exceção nativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|Os dados serão um registro de exceção do Windows de 32 bits.|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|Os dados serão um registro de exceção do Windows de 64 bits.|  
  
## <a name="remarks"></a>Comentários  

 Um membro da `CorDebugRecordFormat` enumeração é passado para o método [DecodeEvent](icordebugprocess6-decodeevent-method.md) para indicar o formato da matriz de bytes em seu `pRecord` argumento.  
  
> [!NOTE]
> Essa enumeração destina-se ao uso em cenários de depuração .NET Native apenas.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Declarando enumerações](debugging-enumerations.md)
