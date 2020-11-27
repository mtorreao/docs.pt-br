---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 0405b4e1207db5c056fbd478b98c408258daf0c3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294203"
---
# <a name="1125---invokemethodisnotstatic"></a>1125 - InvokeMethodIsNotStatic

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1125|  
|Palavras-chave|WFRuntime|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Durante a etapa de CacheMetadata, a atividade de InvokeMethod indica que o método a ser chamado não é estático.  
  
## <a name="message"></a>Mensagem  

 InvokeMethod “%1" - o método não é estático.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|O nome para exibição de atividade de InvokeMethod.|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
