---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235110"
---
# <a name="systemservicemodelmessageprocessingpaused"></a>System.ServiceModel.MessageProcessingPaused

System.ServiceModel.MessageProcessingPaused  
  
## <a name="description"></a>Descrição  

 Os threads foram alternados durante o processamento de uma mensagem.  
  
 O processamento de mensagens pode ser pausado pelos seguintes motivos:  
  
- ConcurrencyMode é Single ou reentrante e o serviço está processando outra mensagem.  
  
- A transação está habilitada e o serviço está processando outra transação.  
  
- O contexto de sincronização não é atual.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
