---
title: 1037 - RuntimeTransactionComplete
ms.date: 03/30/2017
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
ms.openlocfilehash: ad05151a1497ea4b31e0fe33fe2983c1f145f224
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294242"
---
# <a name="1037---runtimetransactioncomplete"></a>1037 - RuntimeTransactionComplete

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1037|  
|Palavras-chave|WFRuntime|  
|Nível|Detalhado|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que a transação de runtime terminado.  
  
## <a name="message"></a>Mensagem  

 A transação de runtime terminou com o estado “%1 ".  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Estado|xs:string|O estado de transação.|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
