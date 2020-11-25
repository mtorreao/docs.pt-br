---
title: Interface ICorDebugILCode2
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: b9289b5afc88c926ce585a4e620364cf2dc979d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703324"
---
# <a name="icordebugilcode2-interface"></a>Interface ICorDebugILCode2

[Com suporte no .NET Framework 4.5.2 e versões posteriores]  
  
 Estende logicamente a interface [ICorDebugILCode](icordebugilcode-interface.md) para fornecer métodos que retornam o token para a assinatura de variável local de uma função e que mapeiam os deslocamentos de Il (linguagem intermediária instrumentada) de um criador de perfil para os deslocamentos de Il do método original.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetInstrumentedILMap](icordebugilcode2-getinstrumentedilmap-method.md)|Retorna um mapa de deslocamentos da IL instrumentada do criador de perfil para os deslocamentos da IL do método original para esta instância.|  
|[Método GetLocalVarSigToken](icordebugilcode2-getlocalvarsigtoken-method.md)|Obtém o token de metadados para a assinatura de variável local para a função que é representada por esta instância.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugILCode](icordebugilcode-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
