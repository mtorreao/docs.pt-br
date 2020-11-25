---
title: Interface ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: 2a5a618491bf2c624669728d97a690cca315bff8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724670"
---
# <a name="icordebugobjectvalue-interface"></a>Interface ICorDebugObjectValue

Uma subclasse de "ICorDebugValue" que representa um valor que contém um objeto.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetClass](icordebugobjectvalue-getclass-method.md)|Obtém um ponteiro de interface para o Common Language Runtime (CLR) <xref:System.Type> do objeto ao qual este `ICorDebugObjectValue` faz referência.|  
|[Método GetContext](icordebugobjectvalue-getcontext-method.md)|Não implementado.|  
|[Método GetFieldValue](icordebugobjectvalue-getfieldvalue-method.md)|Obtém um ponteiro de interface para um [ICorDebugValue](icordebugvalue-interface.md) que representa o valor do campo especificado da classe especificada.|  
|[Método GetManagedCopy](icordebugobjectvalue-getmanagedcopy-method.md)|Obsoleto. Não chame esse método.|  
|[Método GetVirtualMethod](icordebugobjectvalue-getvirtualmethod-method.md)|Não implementado.|  
|[Método IsValueClass](icordebugobjectvalue-isvalueclass-method.md)|Obtém um valor que indica se o objeto referenciado por este `ICorDebugObjectValue` é um tipo de valor.|  
|[Método SetFromManagedCopy](icordebugobjectvalue-setfrommanagedcopy-method.md)|Obsoleto. Não chame esse método.|  
  
## <a name="remarks"></a>Comentários  

 Um `ICorDebugObjectValue` permanece válido até que o processo que está sendo depurado seja continuado.  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
