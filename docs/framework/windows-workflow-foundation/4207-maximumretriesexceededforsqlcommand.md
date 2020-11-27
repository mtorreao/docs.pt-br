---
title: 4207 - MaximumRetriesExceededForSqlCommand
ms.date: 03/30/2017
ms.assetid: 8c8bee26-9ad4-4e01-bd16-0e1fd510fb6b
ms.openlocfilehash: f724379ef2ea23dcca7aa75caab3f10f7635e419
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251198"
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a>4207 - MaximumRetriesExceededForSqlCommand

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|4207|  
|Palavras-chave|Cota, WFInstanceStore|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que o provedor SQL está fornecendo anterior testar de novo um comando SQL como o número máximo de tentativas o foi executado.  
  
## <a name="message"></a>Mensagem  

 Houve uma desistência de tentar um comando SQL como o número máximo de novas tentativas.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
