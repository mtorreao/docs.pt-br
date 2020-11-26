---
title: 1102 - WorkflowActivityStop
ms.date: 03/30/2017
ms.assetid: 285e5cb8-e90d-4914-ac06-e9b176ffefa2
ms.openlocfilehash: 7b5c7874946ae494f41e73f3e7c90f3944a3521d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238685"
---
# <a name="1102---workflowactivitystop"></a>1102 - WorkflowActivityStop

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1102|  
|Palavras-chave|WFRuntime|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que uma atividade de fluxo de trabalho parou.  
  
## <a name="message"></a>Mensagem  

 Identificação de WorkflowInstance: “%1" atividade de E2E  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|A identificação de instância de fluxo de trabalho|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
