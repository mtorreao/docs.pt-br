---
title: Interface ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: ebf484524b32d8e917d88c21425fab314dfc41be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692612"
---
# <a name="icorpublishprocessenum-interface"></a>Interface ICorPublishProcessEnum

Uma subclasse da interface [ICorPublishEnum](icorpublishenum-interface.md) que fornece métodos para atravessar uma coleção de objetos [ICorPublishProcess](icorpublishprocess-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método Next](icorpublishprocessenum-next-method.md)|Obtém o número especificado de `ICorPublishProcess` instâncias da coleção, começando na posição atual.|  
  
## <a name="remarks"></a>Comentários  

 A `ICorPublishProcessEnum` interface implementa os métodos da interface abstrata, [ICorPublishEnum](icorpublishenum-interface.md).  
  
 Uma `ICorPublishProcessEnum` instância é criada pelo método [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) . A passagem da coleção de `ICorPublishProcess` objetos é baseada nos critérios de filtro fornecidos no momento em que a `ICorPublishProcessEnum` instância foi criada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
- [Coclass CorpubPublish](corpubpublish-coclass.md)
