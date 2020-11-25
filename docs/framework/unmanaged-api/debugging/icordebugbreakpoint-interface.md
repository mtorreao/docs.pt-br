---
title: Interface ICorDebugBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 0c84a91c7da553d0c84a4995b4744576d861dcb9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730195"
---
# <a name="icordebugbreakpoint-interface"></a>Interface ICorDebugBreakpoint

Representa um ponto de interrupção em uma função ou um apontador em um valor.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método Activate](icordebugbreakpoint-activate-method.md)|Define o estado ativo deste `ICorDebugBreakpoint` .|  
|[Método IsActive](icordebugbreakpoint-isactive-method.md)|Obtém um valor que indica se ele `ICorDebugBreakpoint` está ativo.|  
  
## <a name="remarks"></a>Comentários  

 Os pontos de interrupção não oferecem suporte direto a expressões condicionais. Se essa funcionalidade for desejada, um depurador deverá implementá-la sobre o `ICorDebugBreakpoint` .  
  
 A interface ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` se estende para dar suporte a pontos de interrupção dentro de funções.  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
