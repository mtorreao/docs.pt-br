---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 23a0113488b1b1ef0bc161d4134b9325ef81406c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236709"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a>Microsoft.Transactions.TransactionBridge.ReplayMessageRetry

Uma nova tentativa de mensagem de reprodução foi enviada a um coordenador sem resposta.  
  
## <a name="description"></a>Descrição  

 Rastreado se o Gerenciador de transações local precisar reenviar uma mensagem de reprodução para um coordenador superior porque ele não recebeu uma resposta em um determinado período de tempo.  
  
## <a name="troubleshooting"></a>Solução de problemas  

 Investigue possíveis problemas de rede ou de produtos que impedem que a resposta seja entregue no prazo.  Se muitas dessas mensagens forem vistas, isso poderá indicar problemas de infraestrutura ou tempos de resposta muito longos. Os dois problemas reduzem drasticamente a taxa de transferência das transações no sistema.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
