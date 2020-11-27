---
title: 'Como: testar o proxy de descoberta'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: b08e8561ceff9f0a427a9ea9acb2309772579853
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294658"
---
# <a name="how-to-test-the-discovery-proxy"></a>Como: testar o proxy de descoberta

Este é o quarto de quatro tópicos que mostra como implementar um proxy de descoberta. No tópico anterior, [como implementar um aplicativo cliente que usa o proxy de descoberta para localizar um serviço](client-app-discovery-proxy-to-find-a-service.md), você implementou um aplicativo cliente WCF que usa o proxy de descoberta para encontrar um serviço e, em seguida, chama o serviço. Este tópico descreve como verificar o proxy de descoberta, o serviço e o aplicativo cliente funcionam conforme o esperado.  
  
### <a name="run-the-discovery-proxy"></a>Executar o proxy de descoberta  
  
1. Abra um prompt de comando como administrador.  
  
2. Você pode ver uma caixa de diálogo que diz: o Firewall do Windows bloqueou alguns recursos deste programa. Se você vir essa mensagem, clique no botão **desbloquear** .  
  
3. No prompt de comando, execute o proxy de descoberta DiscoveryProxy.exe.  
  
4. O aplicativo deve exibir o seguinte texto: `Proxy started. Hit Enter to exit` .  
  
### <a name="run-the-discoverable-service"></a>Executar o serviço detectável  
  
1. Abra um prompt de comando como administrador.  
  
2. No prompt de comando, execute o Service.exe serviço detectável.  
  
3. O DiscoveryProxy.exe deve exibir o texto a seguir: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Executar o aplicativo cliente  
  
1. Abra um prompt de comando.  
  
2. No prompt de comando, execute o aplicativo client.exe.  
  
3. Depois de alguns segundos, o aplicativo cliente exibe o seguinte texto: conectando-se a [Service-Endpoint].  
  
4. O service.exe deve exibir o seguinte texto: solicitação de saudação recebida, responderei.  
  
5. O client.exe deve exibir o seguinte texto: Olá, cliente!  
  
### <a name="shut-down-the-applications"></a>Desligar os aplicativos  
  
1. Desligue o aplicativo cliente.  
  
2. Desligue o serviço. O proxy de descoberta exibe o seguinte texto: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******` .  
  
3. Desligue o proxy de descoberta.  
  
## <a name="see-also"></a>Veja também

- [Visão geral de descoberta do WCF](wcf-discovery-overview.md)
- [Como: implementar um proxy de descoberta](how-to-implement-a-discovery-proxy.md)
- [Como: implementar um serviço de descoberta que registra usando o proxy de descoberta](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [Como: implementar um aplicativo cliente que utiliza o proxy de descoberta para encontrar um serviço](client-app-discovery-proxy-to-find-a-service.md)
