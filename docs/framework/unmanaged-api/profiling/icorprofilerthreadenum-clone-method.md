---
title: Método ICorProfilerThreadEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: de2584b56701f4cffb6a108a5872641ec40e5762
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702518"
---
# <a name="icorprofilerthreadenumclone-method"></a>Método ICorProfilerThreadEnum::Clone

Obtém um ponteiro de interface para uma cópia desta interface [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppEnum`  
 fora Um ponteiro para o ponteiro de interface, que, por sua vez, aponta para a cópia dessa interface [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) . A cópia do enumerador mantém seu próprio estado de enumeração separadamente deste enumerador. No entanto, a posição inicial do cursor da cópia é igual à atual posição do cursor do enumerador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorProf. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)
- [Criação de perfil de interfaces](profiling-interfaces.md)
