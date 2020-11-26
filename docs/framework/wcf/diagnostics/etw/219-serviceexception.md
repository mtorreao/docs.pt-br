---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241935"
---
# <a name="219---serviceexception"></a>219 - ServiceException

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|219|  
|Palavras-chave|EndToEndMonitoring, HealthMonitoring, solução de problemas, ServiceModel|  
|Nível|Erro do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Esse evento é emitido quando um serviço WCF encontra uma exceção sem tratamento. Isso inclui exceções sem tratamento durante a ativação, durante o processamento da mensagem e no código do usuário.  
  
## <a name="message"></a>Mensagem  

 Houve uma exceção sem tratamento do tipo ' %2 ' durante o processamento da mensagem. Exceção ToString completa: %1.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|O resultado de chamada `ToString` () na exceção CLR.|  
|ExceptionTypeName|`xs:string`|O CLR FullName do tipo da exceção.|  
|HostReference|`xs:string`|Para serviços hospedados na Web, esse campo identifica exclusivamente o serviço na hierarquia da Web. Seu formato é definido como ' nome do site aplicativo caminho virtual&#124;serviço caminho virtual&#124;ServiceName '. Exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
