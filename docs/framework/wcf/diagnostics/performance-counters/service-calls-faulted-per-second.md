---
title: 'Serviço: chamadas com falha por segundo'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: d9db777d17de51caff74610d099a79228df1f6d8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252940"
---
# <a name="service-calls-faulted-per-second"></a>Serviço: chamadas com falha por segundo

Nome do contador: chamadas com falha por segundo.  
  
## <a name="description"></a>Descrição  

 Número de chamadas que retornaram falhas para esse serviço em um segundo.  
  
 Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.  
  
 (N 1-N 0)/((D 1-D 0)/F)  
  
 Em aplicativos Windows Communication Foundation (WCF), os métodos de serviço comunicam informações de erro de processamento usando mensagens de falha SOAP. Falhas de SOAP são tipos de mensagem que são incluídos nos metadados de uma operação de serviço e, portanto, criam um contrato de falha que os clientes podem usar para tornar sua execução mais robusta ou interativa. Como as falhas de SOAP são expressas para clientes em formato XML, elas são altamente interoperáveis.  
  
## <a name="see-also"></a>Veja também

- [Especificando e lidando com falhas em contratos e serviços](../../specifying-and-handling-faults-in-contracts-and-services.md)
