---
title: 1101 - WorkflowActivityStart
ms.date: 03/30/2017
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
ms.openlocfilehash: 6e43b0ab1e2d35657bae43e7239a677643154fa9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238724"
---
# <a name="1101---workflowactivitystart"></a>1101 - WorkflowActivityStart

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1101|  
|Palavras-chave|WFRuntime|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que uma atividade de fluxo de trabalho foi iniciado.  
  
## <a name="message"></a>Mensagem  

 Identificação de WorkflowInstance: “%1" atividade de E2E  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|A identificação de instância de fluxo de trabalho|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
