---
title: Contadores de desempenho de ponto de extremidade
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: cdddd8be962df0b295eb394fcaba3756e8a1a50f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237950"
---
# <a name="endpoint-performance-counters"></a>Contadores de desempenho de ponto de extremidade

Os contadores de desempenho de ponto de extremidade capturam dados que revela como um ponto de extremidade está aceitando mensagens. Eles podem ser encontrados no `ServiceModelEndpoint 4.0.0.0` objeto de desempenho ao exibir com o monitor de desempenho. As instâncias são nomeadas usando esse padrão:  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 Os dados são semelhantes aos coletados para operações individuais, mas são agregados somente no ponto de extremidade.  
  
> [!CAUTION]
> Há um limite no comprimento do nome de uma instância do contador de desempenho. Quando um nome de instância de contador de Windows Communication Foundation (WCF) excede o comprimento máximo, o WCF substitui uma parte do nome da instância por um valor de hash.  
  
## <a name="see-also"></a>Veja também

- [Contadores de desempenho](index.md)
