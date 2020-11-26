---
title: Migrando aplicativos remotos .NET para o WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 2cfaebd064d10e5b331412d177929ecb20117a07
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248208"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrando aplicativos remotos .NET para o WCF

**Este tópico é específico para uma tecnologia herdada que é mantida para compatibilidade com versões anteriores com aplicativos existentes e não é recomendada para desenvolvimento novo. Agora, os aplicativos distribuídos devem ser desenvolvidos usando o WCF.**  
  
 Há duas maneiras de aproveitar o WCF com os aplicativos existentes de comunicação remota do .NET: integração e migração. A integração permite que você tenha o .NET Remoting 2,0 e o WCF em execução lado a lado, permitindo que você exponha os mesmos objetos de negócios em ambas as tecnologias simultaneamente, sem a necessidade de modificar seu código .NET Remoting 2,0 existente. A integração requer que você esteja executando o .NET Framework 2,0 ou superior. Se você quiser aproveitar os recursos do WCF e não precisar de compatibilidade de conexão com os sistemas de comunicação remota 2,0, poderá migrar todo o serviço para o WCF. A migração do .NET Remoting 2,0 para o WCF requer alterações na interface do objeto remoto e em suas definições de configuração. Esses dois tópicos são abordados na [comunicação remota com o Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).  
  
## <a name="see-also"></a>Veja também

- [Visão geral conceitual](../conceptual-overview.md)
