---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: e7c92dcc9ce472c50af6f0aa26c59f55d62fbb9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239933"
---
# <a name="1002---workflowapplicationterminated"></a>1002 - WorkflowApplicationTerminated

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1002|  
|Palavras-chave|WFRuntime|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que um aplicativo de fluxo de trabalho foi finalizado no estado criticado com uma exceção.  
  
## <a name="message"></a>Mensagem  

 Identificação de WorkflowApplication: “%1 " foi encerrado. Foi concluído em estado Faulted (com falha) com uma exceção.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|A identificação do aplicativo de fluxo de trabalho|  
|Exceção|`xs:string`|Os detalhes de exceção para a exceção|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
