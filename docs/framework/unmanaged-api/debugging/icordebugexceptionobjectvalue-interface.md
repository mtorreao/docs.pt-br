---
title: Interface ICorDebugExceptionObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 6a0c33799b2b2aaa48e3b18b7b4bb37643508bd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678877"
---
# <a name="icordebugexceptionobjectvalue-interface"></a>Interface ICorDebugExceptionObjectValue

Estende a interface "ICorDebugObjectValue" para fornecer informações de rastreamento de pilha de um objeto de exceção gerenciado.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|Obtém um enumerador para a pilha de chamadas inserido em um objeto de exceção.|  
  
## <a name="remarks"></a>Comentários  

 A chamada para `QueryInterface` terá sucesso para objetos gerenciados que derivam de <xref:System.Exception?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
