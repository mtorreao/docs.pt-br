---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 7ef31a188e1564da47ea1e7323cdd4cd5ef5be60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236670"
---
# <a name="msmq"></a>MSMQ

Em um aplicativo MSMQ, nenhuma atividade adicional é transferida do canal enfileirado para MSMQ e do MSMQ para o canal em fila.  
  
 Além disso, a ID da mensagem do MSMQ e a ID da mensagem SOAP (juntamente com a ID da atividade, se houver) são rastreadas como parte dos rastreamentos de canal na fila em uma operação de envio.  
  
 A ID da mensagem do MSMQ e a ID da mensagem SOAP (juntamente com a ID da atividade, se houver) são rastreadas como parte dos rastreamentos de canal na fila em uma operação de recebimento.  
  
 As transferências necessárias na operação de recebimento são executadas de forma semelhante a qualquer outro transporte (>de mensagens de processo de recebimento de bytes-> operação).
