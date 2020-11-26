---
title: 107 -- BookmarkResumptionRecord
ms.date: 03/30/2017
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
ms.openlocfilehash: 14557ef2726a60bcde49d30f9d6168fd831e613c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238854"
---
# <a name="107----bookmarkresumptionrecord"></a>107 -- BookmarkResumptionRecord

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|107|  
|Palavras-chave|EndToEndMonitoring, solução de problemas, HealthMonitoring, WFTracking|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Este evento é emitido pelo participante de rastreamento de ETW quando uma instância de fluxo de trabalho se emite um BookmarkResumptionRecord.  
  
## <a name="message"></a>Mensagem  

 TrackRecord = BookmarkResumptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, nome = %4, subinstanceid = %5, OwnerActivityName = %6, OwnerActivityId = %7, OwnerActivityInstanceId = %8, OwnerActivityTypeName = %9, anotações = %10, ProfileName = %11  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|A identificação de instância para o fluxo de trabalho|  
|RecordNumber|xs:long|O número de sequência do registro emitido|  
|EventTime|xs:dateTime|A hora UTC quando o evento foi emitido|  
|Nome|xs:string|O nome do indexador que foi que|  
|SubInstanceID|xs:GUID|A identificação do escopo do indexador|  
|OwnerActivityName|xs:string|O nome de atividade do indexador|  
|OwnerActivityId|xs:string|A identificação de atividade do indexador|  
|OwnerActivityInstanceId|xs:string|A identificação de instância de atividade do indexador|  
|OwnerActivityTypeName|xs:string|O tipo de atividade do indexador|  
|Anotações|xs:string|As anotações que foram adicionadas a este evento.  Os valores são armazenados em um elemento XML no formato \<items> \< item  name = "annotationName" type="System.String"> annotationvalue \</item> \</items> .  Se nenhuma anotação for especificada, a cadeia de caracteres conterá \<items/> . O tamanho do evento de ETW é limitado pelo tamanho do buffer de ETW ou pela carga máxima útil para um evento de ETW. Se o tamanho do evento exceder os limites de ETW, o evento será truncado descartando as anotações e substituindo o valor da anotação por \<items> ... \</items> .|  
|ProfileName|xs:string|O nome ou o perfil de rastreamento que levam a este evento que está sendo emitido|  
|HostReference|xs:string|Hospedados para serviços da Web, este campo identifica unicamente o serviço na hierarquia da Web.  Seu formato é definido como ' nome do site aplicativo caminho virtual do serviço&#124;caminho virtual&#124;ServiceName ' exemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
