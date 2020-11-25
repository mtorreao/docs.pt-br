---
title: Interface ICorDebugInternalFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: a17c46d5ef08963bb0d7fc280ba8b90531e41c5b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719626"
---
# <a name="icordebuginternalframe2-interface"></a>Interface ICorDebugInternalFrame2

Fornece informações sobre os quadros internos, incluindo o endereço de pilha e a posição em relação a objetos ICorDebugFrame.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetFrameAddress](icordebuginternalframe2-getframeaddress-method.md)|Retorna o endereço da pilha do quadro interno.|  
|[Método IsCloserToLeaf](icordebuginternalframe2-isclosertoleaf-method.md)|Verifica se o `this` quadro interno está mais próximo da folha do que o objeto ICorDebugFrame especificado.|  
  
## <a name="remarks"></a>Comentários  

 Essa interface estende a interface ICorDebugInternalFrame.  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
