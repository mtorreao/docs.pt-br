---
title: Custom Message Formatters
ms.date: 03/30/2017
ms.assetid: c07435f3-5214-4791-8961-2c2b61306d71
ms.openlocfilehash: e238eb134772c0a95934a460edda62ca9dba2518
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254747"
---
# <a name="custom-message-formatters"></a>Custom Message Formatters

O conteúdo em uma mensagem geralmente está na forma de XML, que geralmente não é um formato conveniente para um aplicativo. Os aplicativos manipulam objetos, obtendo e definindo suas propriedades. Windows Communication Foundation (WCF) usa o *contrato de dados* para converter um <xref:System.ServiceModel.Channels.Message> objeto em um objeto facilmente manipulado por um aplicativo. Esses processos são chamados de serialização e desserialização. Observe que esses mesmos termos são usados para descrever a serialização e desserialização feitas pela camada de transporte de e para o formato de transmissão de mensagem, que é um processo não relacionado.  
  
 Você pode usar um formatador de mensagem personalizado se precisar implementar uma conversão especializada entre mensagens e objetos que você não pode realizar por meio de um contrato de dados. Faça isso modificando ou estendendo o comportamento de execução de uma operação de contrato específica em um cliente ou serviço.  
  
## <a name="custom-message-formatters-on-the-client"></a>Formatadores de mensagem personalizados no cliente  

 A <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface define métodos que são usados para controlar a conversão de mensagens em objetos e objetos em mensagens para aplicativos cliente.  
  
 Você deve implementar essa interface. Primeiro, substitua o <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> método para desserializar uma mensagem. Esse método é chamado depois que uma mensagem de entrada é recebida, mas antes de ser expedida para a operação do cliente.  
  
 Em seguida, substitua o <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> método para serializar um objeto. Esse método é chamado antes do envio de uma mensagem de saída.  
  
 Para inserir o formatador personalizado no aplicativo de serviço, atribua o <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> objeto à <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> propriedade usando um comportamento de operação. Para obter informações sobre comportamentos, consulte [Configurando e estendendo o tempo de execução com comportamentos](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="custom-message-formatters-on-the-service"></a>Formatadores de mensagem personalizada no serviço  

 A <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface define métodos que convertem um <xref:System.ServiceModel.Channels.Message> objeto em parâmetros para uma operação e de parâmetros em um <xref:System.ServiceModel.Channels.Message> objeto em um aplicativo de serviço.  
  
 Você deve implementar essa interface. Primeiro, substitua o <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> método para desserializar uma mensagem. Esse método é chamado depois que uma mensagem de entrada é recebida, mas antes de ser expedida para a operação do cliente.  
  
 Em seguida, substitua o <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> método para serializar um objeto. Esse método é chamado antes do envio de uma mensagem de saída.  
  
 Para inserir o formatador personalizado no aplicativo de serviço, atribua o <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> objeto à <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> propriedade usando um comportamento de operação. Para obter informações sobre comportamentos, consulte [Configurando e estendendo o tempo de execução com comportamentos](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="see-also"></a>Veja também

- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>
- [Configurando e estendendo o runtime com comportamentos](configuring-and-extending-the-runtime-with-behaviors.md)
