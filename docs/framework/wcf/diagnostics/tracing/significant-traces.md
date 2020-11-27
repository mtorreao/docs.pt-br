---
title: Rastreamentos significativos
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: 9ad7c217b528cb2ad22169c1aea6391462bab1ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248664"
---
# <a name="significant-traces"></a>Rastreamentos significativos

Este tópico lista alguns dos principais rastreamentos emitidos por Windows Communication Foundation (WCF).  
  
## <a name="significant-traces"></a>Rastreamentos significativos  
  
|Trace|Descrição|  
|-----------|-----------------|  
|Rastreamento do log de mensagens|O rastreamento é emitido quando uma mensagem do WCF é registrada pelo recurso de log de mensagens quando a `System.ServiceModel.MessageLogging` origem do rastreamento está habilitada. Clicar nesse rastreamento exibe a mensagem. Há quatro pontos de registro em log configuráveis para uma mensagem: `ServiceLevelSendRequest` , `TransportSend` ,, `TransportReceive` `ServiceLevelReceiveRequest` , também indicada pelo atributo origem da mensagem no rastreamento do log de mensagens.|  
|Rastreamento de mensagem recebida|Esse rastreamento é emitido quando uma mensagem do WCF é recebida se a `System.ServiceModel` origem do rastreamento está habilitada no nível de informações ou detalhado. Esse rastreamento é necessário para ver a seta de correlação de mensagem na exibição de gráfico de atividade.|  
|Rastreamento de mensagem enviada|Esse rastreamento é emitido quando uma mensagem do WCF é enviada se a `System.ServiceModel` origem do rastreamento está habilitada no nível de informações ou detalhado. Esse rastreamento é necessário para ver a seta de correlação de mensagem na exibição de gráfico de atividade.|  
|Obter ChannelEndpointElement|Esse rastreamento é emitido na construção de fábrica de canal, no nível de informação. Ele fornece uma descrição do ponto de extremidade ao qual o cliente está se comunicando (endereço remoto, associação, nome do contrato).|  
|Obter ServiceElement|Esse rastreamento é emitido no host do serviço de construção, no nível de informações. Ele fornece uma descrição do contrato de serviço e da associação.|  
|SocketConnection criar|Esse rastreamento é emitido na primeira ação de processo executada pelo cliente e na atividade receber bytes no serviço. Ele fornece os endereços IP locais e remotos. Ele é emitido no nível de informação.|
