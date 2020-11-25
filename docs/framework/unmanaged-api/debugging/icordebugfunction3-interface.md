---
title: Interface ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 17eda7470e5f2e4b41d1f2ed164843eaeeedea93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695863"
---
# <a name="icordebugfunction3-interface"></a>Interface ICorDebugFunction3

[Com suporte no .NET Framework 4.5.2 e versões posteriores]  
  
 Estende a interface de ICorDebugFunction logicamente para fornecer acesso ao código a partir de uma solicitação ReJIT.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetActiveReJitRequestILCode](icordebugfunction3-getactiverejitrequestilcode-method.md)|Obtém um ponteiro de interface para um [ICorDebugILCode](icordebugilcode-interface.md) que contém o Il de uma solicitação de ReJIT ativa.|  
  
## <a name="remarks"></a>Comentários  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
- [ReJIT: um guia de How-To](/archive/blogs/davbr/rejit-a-how-to-guide)
