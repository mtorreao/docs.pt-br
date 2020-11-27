---
title: Estendendo a camada do canal
ms.date: 03/30/2017
helpviewer_keywords:
- extending channels [WCF]
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
ms.openlocfilehash: 8d051ff84ea0562b3d7c810b2c884f4d8b787952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273016"
---
# <a name="extending-the-channel-layer"></a>Estendendo a camada do canal

A camada de canal é responsável pela troca de mensagens entre clientes e serviços. As extensões de canal podem implementar a nova funcionalidade de protocolo, como segurança ou funcionalidade de transporte, como implementar um novo transporte de rede para transportar mensagens SOAP.  
  
## <a name="in-this-section"></a>Nesta seção  

 [Visão geral de modelo de canal](channel-model-overview.md)  
 Fornece uma visão geral de alto nível de quais canais são, os recursos que eles fornecem e como eles funcionam tanto em um serviço quanto em um aplicativo cliente.  
  
 [Canais de desenvolvimento](developing-channels.md)  
 Descreve detalhadamente as funções que os vários tipos de infraestrutura de canal desempenham, como funciona o ciclo de vida de estado e o mecanismo de estado, como lidar com exceções e falhas, como implementar o suporte a metadados e como os canais funcionam com codificadores de mensagem.  
  
 [Decodificadores personalizados](custom-encoders.md)  
 Descreve a função que os codificadores de mensagem desempenham em canais e como criar um.  
  
 [Atualizações de fluxo personalizadas](custom-stream-upgrades.md)  
 Descreve o processo de atualização dos fluxos fornecidos por transportes orientados a fluxo.
