---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 4bb76a93ec7a07a735def1f1d5dc79decb7792ad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239827"
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 - WorkflowApplicationUnhandledException

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1006|  
|Palavras-chave|WFRuntime|  
|Nível|Erro do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que um aplicativo de fluxo de trabalho após uma exceção sem tratamento.  
  
## <a name="message"></a>Mensagem  

 WorkflowInstance ID: ' %1 ' encontrou uma exceção sem tratamento.  A exceção foi originada da atividade ' %2 ', DisplayName: ' %3 '.  A seguinte ação será executada: %4.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|A identificação de instância para o fluxo de trabalho|  
|Exceção|`xs:string`|Os detalhes de exceção para a exceção|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
