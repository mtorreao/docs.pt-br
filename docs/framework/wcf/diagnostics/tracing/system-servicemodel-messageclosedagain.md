---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a8aa5e600789df1b64a8a3f1a6355aaae6a6cf4b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294424"
---
# <a name="systemservicemodelmessageclosedagain"></a>System.ServiceModel.MessageClosedAgain

System.ServiceModel.MessageClosedAgain  
  
## <a name="description"></a>Descrição  

 Uma mensagem foi fechada novamente.  
  
 Uma mensagem deve ser fechada apenas uma vez. Se esse rastreamento estiver sendo emitido no código de extensão do usuário, ele indica que o código de extensão do usuário está fechando uma mensagem que já foi fechada. Se esse rastreamento estiver sendo emitido por meio do código do produto, ele indica que o código de extensão do usuário pode estar fechando uma mensagem muito cedo.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
