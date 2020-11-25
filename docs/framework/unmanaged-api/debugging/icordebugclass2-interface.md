---
title: Interface ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: ce3f289ae914817071fad5274c45d1e5fae71a06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717975"
---
# <a name="icordebugclass2-interface"></a>Interface ICorDebugClass2

Representa uma classe genérica ou uma classe com um parâmetro do método do tipo <xref:System.Type>. Essa interface estende [ICorDebugClass](icordebugclass-interface.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método GetParameterizedType](icordebugclass2-getparameterizedtype-method.md)|Obtém a declaração de tipo para esta classe.|  
|[Método SetJMCStatus](icordebugclass2-setjmcstatus-method.md)|Para cada método dessa classe, define um valor que indica se o método é um código definido pelo usuário.|  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugClass](icordebugclass-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
