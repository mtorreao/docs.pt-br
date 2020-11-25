---
title: Método IHostTaskManager::BeginDelayAbort
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
ms.openlocfilehash: f72cc15904d098e159dd7f75f673d43ae987998d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727322"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a>Método IHostTaskManager::BeginDelayAbort

Notifica o host de que o código gerenciado está entrando em um período no qual a tarefa atual não deve ser anulada.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a>Valor retornado  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|`BeginDelayAbort` retornado com êxito.|  
|HOST_E_CLRNOTAVAILABLE|O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.|  
|HOST_E_TIMEOUT|A chamada atingiu o tempo limite.|  
|HOST_E_NOT_OWNER|O chamador não possui o bloqueio.|  
|HOST_E_ABANDONED|Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.|  
|E_FAIL|Ocorreu uma falha catastrófica desconhecida. Quando um método retorna E_FAIL, o CLR não é mais utilizável no processo. As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.|  
|E_UNEXPECTED|`BeginDelayAbort` Já foi chamado, mas a chamada correspondente a [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) ainda não foi recebida.|  
  
## <a name="remarks"></a>Comentários  

 O host não deve abortar a tarefa atual até que `EndDelayAbort` seja chamado. Se outra chamada para `BeginDelayAbort` for feita sem uma chamada intermediária para `EndDelayAbort` , o host deverá retornar E_UNEXPECTED de `BeginDelayAbort` e não deverá executar nenhuma ação.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRTask](iclrtask-interface.md)
- [Interface ICLRTaskManager](iclrtaskmanager-interface.md)
- [Interface IHostTaskManager](ihosttaskmanager-interface.md)
