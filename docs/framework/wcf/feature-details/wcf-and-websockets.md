---
title: WCF e WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: 2ee27eef015ee8c2fbee8360b444343a1c757097
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281580"
---
# <a name="wcf-and-websockets"></a>WCF e WebSockets

O .NET Framework 4.5 introduz suporte para WebSockets no Windows Communication Foundation.  WebSockets é uma tecnologia eficiente e com base em padrões que permite a comunicação bidirecional sobre as portas HTTP padrão 80 e 443. O uso de portas HTTP padrão permite que o WebSockets comunique-se por meio da Web por meio de intermediários.  Duas novas associações padrão foram adicionadas à comunicação de suporte em um transporte de WebSocket. <xref:System.ServiceModel.NetHttpBinding> e <xref:System.ServiceModel.NetHttpsBinding>. As configurações específicas do WebSocket podem ser configuradas no <xref:System.ServiceModel.Channels.HttpTransportBindingElement> acessando a <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> propriedade.
  
## <a name="in-this-section"></a>Nesta seção  

 [Usando o NetHttpBinding](using-the-nethttpbinding.md)  
 Discute o <xref:System.ServiceModel.NetHttpBinding> e como configurá-lo.  
  
 [Como: criar um serviço WCF que se comunica por meio de WebSockets](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Descreve como criar um serviço WCF que se comunica sobre Websockets.  
  
## <a name="reference"></a>Referência  
  
## <a name="related-sections"></a>Seções relacionadas
