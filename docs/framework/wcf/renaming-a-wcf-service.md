---
title: Renomeando um serviço do WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 25f9201253f02f368ccf95ddf1f7a7d78d2e1b2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249716"
---
# <a name="renaming-a-wcf-service"></a>Renomeando um serviço do WCF

Este tópico descreve como você pode renomear um serviço do Windows Communication Foundation (WCF).  
  
## <a name="renaming-a-wcf-service"></a>Renomeando um serviço do WCF  

 Execute as seguintes etapas para renomear um serviço em um modelo Windows Communication Foundation (WCF),  
  
- Altere o nome da classe que implementa o serviço.  
  
- No arquivo de configuração do serviço, altere o nome do serviço para o novo nome que você escolheu, conforme indicado no exemplo a seguir. O arquivo de configuração pode ser app.config ou web.config arquivo, dependendo do modelo de hospedagem.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- Se o serviço for webhostd, ele usará um arquivo *\* . svc* . Abra o arquivo svc e modifique o nome do serviço, conforme indicado no exemplo a seguir. Essa etapa não é necessária para aplicativos hospedados internamente, pois não há nenhum arquivo svc.  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Renomeando um contrato de serviço WCF  
  
- Execute as seguintes etapas para renomear o contrato de serviço,  
  
- Altere o nome do contrato de serviço.  
  
- No arquivo de configuração do serviço, altere o nome do contrato de serviço para o novo nome que você escolheu, conforme indicado no exemplo a seguir. O arquivo de configuração pode ser app.config ou web.config arquivo, dependendo do modelo de hospedagem.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
