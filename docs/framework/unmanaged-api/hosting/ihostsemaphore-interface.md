---
title: Interface IHostSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: cccbf9a28b16ffee14b3fd3ec43c376109d6ccec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683050"
---
# <a name="ihostsemaphore-interface"></a>Interface IHostSemaphore

Representa a implementação do host de um semáforo para Threading.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)|Aumenta a contagem da instância atual `IHostSemaphore` pelo valor especificado.|  
|[Método Wait](ihostsemaphore-wait-method.md)|Faz com que a `IHostSemaphore` instância atual aguarde até que ela seja propriedade ou a quantidade especificada de tempo decorre.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRSyncManager](iclrsyncmanager-interface.md)
- [Interface IHostAutoEvent](ihostautoevent-interface.md)
- [Interface IHostManualEvent](ihostmanualevent-interface.md)
- [Interface IHostSyncManager](ihostsyncmanager-interface.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
