---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: aeeba38eaf674453f4c87cf62f5088c55b5fde2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290810"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed

Não é possível mover ou excluir a mensagem.  
  
## <a name="description"></a>Descrição  

 O rastreamento indica que uma falha ocorreu ao tentar mover, excluir ou rejeitar uma mensagem MSMQ.  
  
 As mensagens MSMQ são empregadas por Windows Communication Foundation (WCF) (quando usadas com NetMsmqBinding ou MsmqIntegrationBinding). Esse rastreamento está relacionado ao valor escolhido da `ReceiveErrorHandling` propriedade em NetMsmqBinding ou MsmqIntegrationBinding.  
  
 Esse rastreamento não indica uma falha geral do sistema. No entanto, isso indica que a disposição de mensagem suspeita escolhida falhou para uma mensagem. Para obter mais informações sobre quando as mensagens se tornam suspeitas e como configurar seu serviço para tratá-las adequadamente, consulte [manipulação de mensagens suspeitas](../../feature-details/poison-message-handling.md).  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
