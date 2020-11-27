---
title: 4214 - InstanceLocksRecoveryError
ms.date: 03/30/2017
ms.assetid: d28fb2d5-bf15-4648-8d20-8141ad16f04b
ms.openlocfilehash: 4449232e5aed67f73936c5b93181f7852b164ad7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264108"
---
# <a name="4214---instancelocksrecoveryerror"></a>4214 - InstanceLocksRecoveryError

## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|4214|  
|Palavras-chave|WFInstanceStore|  
|Nível|Erro do|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  

 Recuperando os bloqueios de instância falhados devido a uma exceção.  
  
## <a name="message"></a>Mensagem  

 Falha na recuperação dos bloqueios de instância devido à seguinte exceção  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Exceção|xs:string|Os detalhes de exceção para a exceção|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
