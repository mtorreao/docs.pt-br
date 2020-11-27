---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 2192b63b8a08657b69f6e3984f898bd6baddbc5f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294177"
---
# <a name="1131---invokemethoduseasyncpattern"></a>1131 - InvokeMethodUseAsyncPattern

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1131|  
|Palavras-chave|WFRuntime|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Durante a etapa de CacheMetadata, a atividade de InvokeMethod indica que está usando o padrão de async ao chamar o método.  
  
## <a name="message"></a>Mensagem  

 InvokeMethod “%1 " - o método utiliza o padrão assíncrono de “%2 " e “%3 ".  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|O nome para exibição de atividade de InvokeMethod.|  
|BeginMethod|xs:string|O nome do método inicial.|  
|EndMethod|xs:string|O nome do método final.|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
