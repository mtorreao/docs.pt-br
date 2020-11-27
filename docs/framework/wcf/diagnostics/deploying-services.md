---
title: Implantando serviços
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 07bd2a3938f238336dc00fa2e0826a28a9363a4a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294801"
---
# <a name="deploying-services"></a>Implantando serviços

Este tópico descreve como você pode implantar um aplicativo Windows Communication Foundation (WCF) em um ambiente de tempo de execução.  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a>Escolhendo o ambiente de hospedagem para seu aplicativo  

 Os serviços WCF são projetados para serem executados em qualquer processo do Windows que ofereça suporte a código gerenciado. Para se tornar ativo, um serviço deve ser hospedado em um ambiente de tempo de execução que o cria e controla seu contexto e vida útil. As opções de hospedagem variam da execução dentro do aplicativo de console mais simples para ambientes de servidor como um serviço do Windows, Serviços de Informações da Internet (IIS) ou dentro de um processo de trabalho gerenciado pelo WAS (serviço de ativação do Windows). Para examinar as diferentes opções de hospedagem para seu aplicativo WCF, consulte [serviços de hospedagem](../hosting-services.md).  
  
## <a name="see-also"></a>Veja também

- [Hosting](../feature-details/hosting.md)
- [Serviços de hospedagem](../hosting-services.md)
