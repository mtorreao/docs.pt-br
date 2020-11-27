---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: 64b41ee78e943ca16eaa791133454ec62ccf6ed8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263081"
---
# <a name="222---operationfailed"></a>222 - OperationFailed

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|222|  
|Palavras-chave|EndToEndMonitoring, HealthMonitoring, solução de problemas, ServiceModel|  
|Nível|Aviso|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Esse evento é emitido quando o padrão do modelo de serviço `OperationInvoker` encontrou uma exceção ao invocar seu método. Observe que as exceções que derivam de `FaultException` fazem com que esse evento não seja emitido.  
  
## <a name="message"></a>Mensagem  

 O método ' %1 ' lançou uma exceção sem tratamento quando invocado pelo OperationInvoker. A duração da chamada do método era ' %2 ' MS.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Nome do método|`xs:string`|O nome do CLR do método que foi invocado pelo `OperationInvoker` .|  
|Duração|`xs:long`|O tempo, em milissegundos, necessário `OperationInvoker` para invocar o método.|  
|HostReference|`xs:string`|Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web. Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '. Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
