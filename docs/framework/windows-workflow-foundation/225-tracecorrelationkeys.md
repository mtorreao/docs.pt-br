---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 04c5e0f4fbf3b95485e5bf4aae53aa2e4912d893
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294489"
---
# <a name="225---tracecorrelationkeys"></a>225 - TraceCorrelationKeys

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|225|  
|Palavras-chave|Solução de problemas, ServiceModel|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Este evento é emitida quando correlação conteudo base é usada para um serviço de fluxo de trabalho. Contém as chaves de correlação que são aplicadas para correlacionar uma mensagem a uma instância.  
  
## <a name="message"></a>Mensagem  

 Chave calculada “%1 " de correlação usando o %2 " dos valores no escopo pai “%3 ".  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Chave de instância|`xs:GUID`|A tecla que foi gerada de correlação avalia.|  
|Valores|`xs:string`|Os valores que foram usados para calcular a chave de instância de correlação.|  
|Escopo pai|`xs:string`||  
|HostReference|`xs:string`|Os serviços hospedados da Web, este campo identificam exclusivamente o serviço na hierarquia da Web. Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '. Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
