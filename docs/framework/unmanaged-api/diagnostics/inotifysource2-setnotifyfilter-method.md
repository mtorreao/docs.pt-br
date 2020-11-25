---
title: Método INotifySource2::SetNotifyFilter
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
ms.openlocfilehash: 99bce831405d722f1f1ca0ae56e60f95f2d905e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719925"
---
# <a name="inotifysource2setnotifyfilter-method"></a>Método INotifySource2::SetNotifyFilter

Atribui um filtro de notificação para uso com esta origem.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `in_NotifyFilter`  
 no Uma combinação de bits bit a [NOTIFY_FILTER](notify-filter-enumeration.md) valores de enumeração que identificam retornos de chamada para a API do depurador.  
  
 `in_pUserThreadFilter`  
 no Um ponteiro para uma estrutura de [USER_THREAD](user-thread-structure.md) que identifica threads para a API do depurador.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Confira também

- [Interface INotifySource2](inotifysource2-interface.md)
- [Interface INotifyConnection2](inotifyconnection2-interface.md)
- [Interface INotifySink2](inotifysink2-interface.md)
