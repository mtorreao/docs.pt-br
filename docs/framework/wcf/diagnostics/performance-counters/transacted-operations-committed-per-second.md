---
title: Operações Transacionadas Confirmadas por Segundo
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: deb29820aab09adad8825a299145772892117948
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250002"
---
# <a name="transacted-operations-committed-per-second"></a>Operações Transacionadas Confirmadas por Segundo

Nome do contador: operações transacionadas confirmadas por segundo.  
  
## <a name="description"></a>Descrição  

 Número de operações transacionais que foram confirmadas neste serviço em um segundo.  
  
 Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.  
  
 (N 1-N 0)/((D 1-D 0)/F)
