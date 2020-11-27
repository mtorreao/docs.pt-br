---
title: Adulteração
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: c2b0cae1dc57fac486122ca17fc8109ffe62f77d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249794"
---
# <a name="tampering"></a>Adulteração

A *violação* é o ato de alterar uma mensagem ou a entrega de uma mensagem, e usar a mensagem alterada para uma finalidade diferente da que foi pretendida.  
  
## <a name="do-not-disable-ws-addressing"></a>Não desabilitar WS-Addressing  

 A especificação de WS-Addressing fornece cabeçalhos de endereço em cada mensagem, permitindo que um destinatário da mensagem Verifique o remetente da mensagem. Você pode desabilitar esse recurso definindo a <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> propriedade como <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> .  
  
 Quando o modo de segurança é definido como Message e, se WS-Addressing estiver desabilitado, um invasor poderá receber uma solicitação de um cliente e enviá-lo para outro serviço, e o segundo serviço não terá como detectar se a mensagem veio do cliente original. Na verdade, o primeiro serviço pode fingir que é um cliente ao conversar com o segundo serviço.  
  
 Para atenuar isso, nunca defina a <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> propriedade como <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> e evite o uso de <xref:System.ServiceModel.Channels.MessageVersion> , como a <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> propriedade estática, que define a <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> propriedade como <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> .  
  
## <a name="see-also"></a>Veja também

- [Considerações sobre segurança](security-considerations-in-wcf.md)
- [Divulgação de Informações Confidenciais](information-disclosure.md)
- [Elevação de Privilégio](elevation-of-privilege.md)
- [Negação de Serviço](denial-of-service.md)
- [Cenários sem suporte](unsupported-scenarios.md)
- [Ataques por repetição](replay-attacks.md)
