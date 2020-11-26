---
title: 403 - SuspendSignpostEvent
ms.date: 03/30/2017
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
ms.openlocfilehash: 66251141cdf66c18ad0c1334f6f3e6c0629b4b33
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241051"
---
# <a name="403---suspendsignpostevent"></a>403 - SuspendSignpostEvent

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|403|  
|Palavras-chave|Solução de problemas|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  

 Esse evento marca a suspensão de uma atividade de ponta a ponta. Contém o nome da atividade.  
  
## <a name="message"></a>Mensagem  

 Limite de atividade.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Dados estendidos|`xs:string`|O nome da atividade.|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
