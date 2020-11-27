---
title: 'Ponto de extremidade: chamadas com falha por segundo'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 0aeafa3d273ae22d9bbfe5e3edbac80c6e4851bd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271247"
---
# <a name="endpoint-calls-failed-per-second"></a>Ponto de extremidade: chamadas com falha por segundo

Nome do contador: chamadas com falha por segundo.  
  
## <a name="description"></a>Descrição  

 Número de chamadas que têm exceções sem tratamento e são recebidas por esse ponto de extremidade em um segundo.  
  
 Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.  
  
 (N 1-N 0)/((D 1-D 0)/F)  
  
 Esse contador é incrementado toda vez que há uma exceção sem tratamento neste ponto de extremidade.  
  
## <a name="see-also"></a>Veja também

- [Especificando e lidando com falhas em contratos e serviços](../../specifying-and-handling-faults-in-contracts-and-services.md)
