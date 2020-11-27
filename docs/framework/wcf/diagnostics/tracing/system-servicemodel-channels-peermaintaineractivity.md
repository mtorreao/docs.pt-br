---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: c1e82611bb776531ad3e3d60283d970602eb7f15
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293020"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a>System.ServiceModel.Channels.PeerMaintainerActivity

O módulo PeerMaintainer está executando uma operação específica (detalhes contidos no corpo da mensagem de rastreamento).  
  
## <a name="description"></a>Descrição  

 Esse rastreamento ocorre durante várias operações de PeerMaintainer.  
  
 PeerMaintainer é um componente interno do PeerNode. A cada minuto, ou a cada 32 mensagens recebidas, ele envia uma mensagem LinkUtility para seus vizinhos com estatísticas sobre quantas mensagens são trocadas e quantos são úteis (não duplicados, não violados). Isso ajuda a determinar o utilitário de link de um vizinho específico. Aproximadamente a cada cinco minutos, o mantenedor verifica a integridade das conexões vizinhas. Se o número de conexões vizinhas exceder o valor ideal, o mantenedor removerá as conexões menos úteis. Se não houver conexões suficientes, o mantenedor adquirirá novas conexões.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
