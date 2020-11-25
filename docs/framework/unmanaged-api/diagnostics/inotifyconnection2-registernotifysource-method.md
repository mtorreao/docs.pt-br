---
title: Método INotifyConnection2::RegisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: 1286dd970e437af0a8b607ed050ab4838f73a41f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720042"
---
# <a name="inotifyconnection2registernotifysource-method"></a>Método INotifyConnection2::RegisterNotifySource

Instala uma fonte de notificação especificada.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `in_pNotifySource`  
 no Especifica o objeto a ser usado como a fonte de notificação.  
  
 `out_ppNotifySink`  
 fora Recebe o objeto a ser usado como o coletor de notificação.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Confira também

- [Interface INotifyConnection2](inotifyconnection2-interface.md)
- [Interface INotifySource2](inotifysource2-interface.md)
- [Interface INotifySink2](inotifysink2-interface.md)
- [Método UnregisterNotifySource](inotifyconnection2-unregisternotifysource-method.md)
