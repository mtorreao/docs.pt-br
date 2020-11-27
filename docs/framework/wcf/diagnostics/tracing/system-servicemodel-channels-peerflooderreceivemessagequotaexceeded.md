---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: d4fbbeaaa1daeea62b5495d0b30c37d0297ccd75
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249911"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded

A taxa de recebimento de mensagens de entrada é muito alta.  
  
## <a name="description"></a>Descrição  

 Esse rastreamento ocorre ao tentar processar mensagens de entrada. Uma mensagem não pôde ser encaminhada para um vizinho específico porque o conjunto de cotas para esse vizinho foi excedido. Isso ocorre quando um vizinho sem resposta falha ao limpar uma pendência de mensagens pendentes para esse vizinho.  
  
## <a name="troubleshooting"></a>Solução de problemas  

 Reduza a taxa em que as mensagens são enviadas dentro da malha.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
