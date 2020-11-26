---
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 26b860b88313a971960a65b599562ef1ccb4e7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243515"
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|224|  
|Palavras-chave|EndToEndMonitoring, HealthMonitoring, solução de problemas, ServiceModel|  
|Nível|Aviso|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Quando uma das principais restrições de serviço for excedida, o `MessageThrottleExceeded` evento será emitido. Quando o pico de atividade é lento e o valor atual da limitação está em 70% do limite atual, esse evento é emitido. Observe que esse evento é emitido apenas uma vez, pois a atividade está lenta. Se o valor atual focalizar na marca de porcentagem de 70, (por exemplo, 70, 69, 70, 71, 70, 69), somente a primeira ocorrência de 70% resultará em um evento. Depois que esse evento é emitido, ocorrências futuras de exceder o limite do acelerador resulta em um `MessageThrottleExceeded` evento.  
  
## <a name="message"></a>Mensagem  

 O limite de ' %2 ' do acelerador ' %1 ' está em 70%%.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Nome do acelerador|`xs:string`|O nome do limite que foi excedido. `MaxConcurrentCalls`Ou, `MaxConcurrentInstances` , ou `MaxConcurrentSessions` ,|  
|Limite|`xs:long`|O limite atualmente configurado da limitação.|  
|HostReference|`xs:string`|Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web. Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '. Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
