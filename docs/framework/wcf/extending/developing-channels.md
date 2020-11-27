---
title: Canais de desenvolvimento
ms.date: 03/30/2017
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
ms.openlocfilehash: 11e7a78282a3c9f7cd221e2ef44bc43c625e447b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286793"
---
# <a name="developing-channels"></a>Canais de desenvolvimento

O desenvolvimento de um protocolo ou canal de transporte que pode ser usado com a camada de aplicativo Windows Communication Foundation (WCF) requer várias etapas. Este tópico descreve essas etapas e aponta para tópicos específicos para obter mais informações. Para entender o modelo de canal e os vários tipos mencionados neste tópico, consulte [visão geral do modelo de canal](channel-model-overview.md). Para obter um exemplo de canal de transporte completo, consulte [transporte: UDP](../samples/transport-udp.md).  
  
## <a name="the-channel-development-task-list"></a>O Lista de Tarefas de desenvolvimento de canal  

 As etapas para criar um canal definido pelo usuário são as seguintes. Todos os canais devem:  
  
1. Decida qual dos padrões de troca de mensagens do canal ( <xref:System.ServiceModel.Channels.IOutputChannel> , <xref:System.ServiceModel.Channels.IInputChannel> , <xref:System.ServiceModel.Channels.IDuplexChannel> , <xref:System.ServiceModel.Channels.IRequestChannel> ou <xref:System.ServiceModel.Channels.IReplyChannel> ) seu <xref:System.ServiceModel.Channels.IChannelFactory> e <xref:System.ServiceModel.Channels.IChannelListener> dará suporte, bem como se ele dará suporte às variações de sessão dessas interfaces. Para obter detalhes, consulte [escolhendo um padrão de troca de mensagens](choosing-a-message-exchange-pattern.md).  
  
2. Crie uma fábrica de canais e um ouvinte ( <xref:System.ServiceModel.Channels.IChannelFactory> e <xref:System.ServiceModel.Channels.IChannelListener> ) que ofereçam suporte ao seu padrão de troca de mensagens. Para obter detalhes sobre o desenvolvimento de fábricas, consulte [cliente: fábricas de canal e canais](client-channel-factories-and-channels.md). Para obter detalhes sobre como desenvolver ouvintes, consulte [serviço: ouvintes de canal e canais](service-channel-listeners-and-channels.md).  
  
3. Certifique-se de que qualquer exceção específica da rede seja normalizada para <xref:System.TimeoutException?displayProperty=nameWithType> ou para a classe derivada apropriada do <xref:System.ServiceModel.CommunicationException> . Para obter detalhes, consulte [tratamento de exceções e falhas](handling-exceptions-and-faults.md).  
  
4. Para habilitar o uso da camada de aplicativo, adicione um <xref:System.ServiceModel.Channels.BindingElement> que adiciona o canal personalizado a uma pilha de canais. Para obter mais informações, consulte [criando um BindingElement](creating-a-bindingelement.md).  
  
 As etapas adicionais a seguir são necessárias para habilitar o suporte mais completo na camada de aplicativo:  
  
1. Adicione uma seção de extensão de elemento de associação para expor o novo elemento de associação ao sistema de configuração. Para obter mais informações, consulte [suporte de configuração e metadados](configuration-and-metadata-support.md).  
  
2. Adicione extensões de metadados para comunicar recursos a outros pontos de extremidade. Para obter mais informações, consulte [suporte de configuração e metadados](configuration-and-metadata-support.md).  
  
3. Adicione uma associação que predefine uma pilha de elementos de associação de acordo com um perfil bem definido. Para obter mais informações, consulte [Criando associações de User-Defined](creating-user-defined-bindings.md).  
  
4. Adicione uma seção de associação e um elemento de configuração de associação para expor a associação ao sistema de configuração. Para obter mais informações, consulte [suporte de configuração e metadados](configuration-and-metadata-support.md).  
  
## <a name="see-also"></a>Veja também

- [Estendendo associações](extending-bindings.md)
