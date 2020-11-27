---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: c36294a4a430c3e372e8213246e85dba45ce03c8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286013"
---
# <a name="205---operationinvoked"></a>205 - OperationInvoked

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|205|  
|Palavras-chave|Solução de problemas, ServiceModel|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Esse evento é emitido logo antes de o padrão do modelo de serviço `OperationInvoker` iniciar uma chamada para um método.  
  
## <a name="message"></a>Mensagem  

 Um OperationInvoker invocou o método ' %1 '. Informações do chamador: ' %2 '.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Nome do método|`xs:string`|O nome do CLR do método que foi invocado pelo `OperationInvoker` .|  
|Informações de chamador|`xs:string`|O endereço IP e o número da porta do cliente no formato ' IPAddress: PortNumber '. Os dois valores são recuperados da propriedade de mensagem ' System. ServiceModel. Channels. RemoteEndpointMessageProperty ' dentro do contexto de operação. Observe que, para associações não TCP, esse valor `null` .|  
|HostReference|`xs:string`|Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web. Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '. Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
