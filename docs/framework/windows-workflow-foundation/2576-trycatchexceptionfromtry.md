---
title: 2576 - TryCatchExceptionFromTry
ms.date: 03/30/2017
ms.assetid: 47e48973-b17c-4a16-8338-c84b54aa0a6e
ms.openlocfilehash: 722d5206322c2a9abacbca554d489ba2f6efe357
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235825"
---
# <a name="2576---trycatchexceptionfromtry"></a>2576 - TryCatchExceptionFromTry

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|2576|  
|Palavras-chave|WFActivities|  
|Nível|Informações do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Indica que a atividade de TryCatch capturou uma exceção.  
  
## <a name="message"></a>Mensagem  

 A atividade “%1 " de TryCatch capturou uma exceção “%2 ".  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|O nome para exibição de atividade.|  
|Exceção|xs:string|O nome do tipo de exceção.|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
