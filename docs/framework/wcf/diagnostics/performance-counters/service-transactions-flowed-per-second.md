---
title: 'Serviço: fluxo de transações por segundo'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 158bd7e2f2f98e91215ef7351cf90493a2d3059d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236826"
---
# <a name="service-transactions-flowed-per-second"></a>Serviço: fluxo de transações por segundo

Nome do contador: transações fluidas por segundo.  
  
## <a name="description"></a>Descrição  

 Número de transações fluidas para operações neste serviço em um segundo.  
  
 Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.  
  
 (N 1-N 0)/((D 1-D 0)/F)
