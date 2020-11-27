---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: d8edb8e916578247e62e3a3eb3b11b80f93416cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286949"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException

Ocorreu uma exceção ao fechar as conexões nesse pool de conexões.  
  
## <a name="description"></a>Descrição  

 Esse rastreamento de nível de erro indica que ocorreu um erro ao fechar os pools de conexão usados pelo recurso de pool de conexões do Windows Communication Foundation (WCF). Um motivo possível para isso é um fechamento malsucedido de uma conexão em pool ou um conjunto de conexões em pool dentro do CloseTimeout. Quando essa exceção é lançada, todas as conexões não fechadas restantes dentro desse pool são anuladas; as conexões não fechadas em outros pools são abandonadas.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
