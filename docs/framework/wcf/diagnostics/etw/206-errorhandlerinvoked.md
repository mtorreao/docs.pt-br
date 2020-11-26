---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 99415733624752217d32f6f026a419b2b32bfa7b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244607"
---
# <a name="206---errorhandlerinvoked"></a>206 - ErrorHandlerInvoked

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|206|  
|Palavras-chave|Solução de problemas, ServiceModel|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Esse evento é emitido após uma `ErrorHandler` oportunidade de lidar com uma exceção que ocorreu em uma operação de serviço.  
  
## <a name="message"></a>Mensagem  

 O Dispatcher invocou um ErrorHandler do tipo ' %1 ' com uma exceção do tipo ' %3 '. ErrorHandled = = ' %2 '.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|O CLR FullName do tipo do chamado `ErrorHandler` .|  
|Manipulado|`xs:unsignedByte`|`true` Se o manipulador de erros tratou o erro, caso contrário `false` .|  
|ExceptionTypeName|`xs:string`|O CLR FullName da exceção que estava sendo tratada.|  
|HostReference|`xs:string`|Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web. Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '. Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
