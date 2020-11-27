---
title: 'Ponto de extremidade: mensagens de segurança não autorizadas'
ms.date: 03/30/2017
ms.assetid: d25095ff-9ff0-4c69-a674-4e6a9fe3f4dc
ms.openlocfilehash: 3979eec15759989b638e1cc813cb78a0c008c3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256502"
---
# <a name="endpoint-security-calls-not-authorized"></a>Ponto de extremidade: mensagens de segurança não autorizadas

Nome do contador: chamadas de segurança não autorizadas.  
  
## <a name="description"></a>Descrição  

 Esse contador é incrementado quando o <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> método retorna `false` . Isso indica que a mensagem de entrada é de um usuário válido e protegida corretamente, mas o usuário não está autorizado a realizar tarefas específicas.
