---
title: Enumeração CorDebugMDAFlags
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: 1bb99503481d917d41ae00a5ef73c8fa59e2a999
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696447"
---
# <a name="cordebugmdaflags-enumeration"></a>Enumeração CorDebugMDAFlags

Especifica o status do thread no qual o assistente de depuração gerenciada (MDA) é disparado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|O thread no qual o MDA foi acionado foi adiado desde que o MDA foi acionado.|  
  
## <a name="remarks"></a>Comentários  

 Quando a pilha de chamadas não descreve mais onde o MDA foi gerado originalmente, o thread é considerado como tendo sido *adiado*. Essa é uma circunstância incomum apresentada pela execução do thread de uma operação inválida na saída.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Declarando enumerações](debugging-enumerations.md)
