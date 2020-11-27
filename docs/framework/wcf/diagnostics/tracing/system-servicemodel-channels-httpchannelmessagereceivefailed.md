---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 97f22a01df84c39915f74fa7677e5dd18154b952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256216"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed

Falha ao receber uma mensagem por um canal HTTP.  
  
## <a name="description"></a>Descrição  

 Esse rastreamento pode ser emitido como um aviso ou um erro. Em ambos os casos, o rastreamento é emitido quando um ouvinte compatível não é encontrado para uma solicitação HTTP de entrada e a solicitação HTTP é descartada. Isso pode acontecer porque o verbo HTTP da solicitação não foi reconhecido por nenhum ouvinte HTTP ou porque nenhum ouvinte estava escutando no endereço para o qual a solicitação foi destinada. O rastreamento é emitido como um aviso no caso hospedado automaticamente e como um erro quando o serviço é hospedado no IIS.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
