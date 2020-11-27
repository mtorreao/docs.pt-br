---
title: Adicionando status online e offline
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: 08ae4a20ced9626504c9fd2045416460e0878c5b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292916"
---
# <a name="adding-online-and-offline-status"></a>Adicionando status online e offline

Em muitos casos, é importante que um aplicativo monitore detalhes específicos sobre o status de uma conexão de canal de mesmo nível. Você pode obter essas informações chamando o `GetProperty` método em uma implementação da <xref:System.ServiceModel.IOnlineStatus> interface. Um objeto com uma implementação dessa interface pode monitorar o status da conexão ou registrar-se para manipuladores de eventos, como `OnOnline` e e `OnOffline` reagir imediatamente conforme as alterações no status online ocorrem.  
  
 Na infraestrutura de canal par, um cliente será considerado online se estiver conectado a pelo menos um outro par e offline do contrário. Isso pode ser particularmente útil na depuração de aplicativos de desenvolvimento ou na exibição de informações detalhadas para o usuário final.  
  
> [!NOTE]
> Um manipulador de eventos online deve primeiro garantir que o nó esteja aberto antes de enviar qualquer mensagem.  
  
## <a name="see-also"></a>Veja também

- [Compilando um aplicativo de canal par](building-a-peer-channel-application.md)
