---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: b8bf8431c4e2b82c6aac95820eb45de2a404e976
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294268"
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1035|  
|Palavras-chave|WFRuntime|  
|Nível|Detalhado|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que uma atividade definiu a transação de runtime.  
  
## <a name="message"></a>Mensagem  

 A transação de tempo de execução foi definida pela atividade ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  Execução isolada para a atividade ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 '.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Atividade|xs:string|O nome do tipo de atividade.|  
|DisplayName|xs:string|O nome para exibição de atividade.|  
|InstanceId|xs:string|A identificação de instância de atividade.|  
|IsolatedActivity|xs:string|O nome do tipo de que a atividade isolada a transação está.|  
|IsolatedActivityDisplayName|xs:string|O nome para exibição de que a atividade isolada a transação está.|  
|IsolatedActivityInstanceId|xs:string|A identificação de instância de que a atividade isolada a transação está.|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
